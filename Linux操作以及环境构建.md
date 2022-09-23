# Linux操作まとめ

## 常用的Linux命令

### 查看当前Linux系统的版本的方法

```shell
cat /proc/version 
```

### 查看端口号

```shell
netstat -tunlp | grep 8000
```

### 删除操作

```shell
find / -name gitlab | xargs rm -rf
```

### 删除文件夹

```shell
rm -rf 文件夹名
```



### 查找操作

```shell
whereis xxxx
```

### 安装vim

```shell
sudo apt-get install vim
```

## 安装Docker

### 获取软件最新源

```shell
sudo apt-get update
```

### 安装包允许apt通过HTTPS使用仓库安装依赖

```shell
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```

### 添加Docker的官方GPG密钥

```shell
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### 设置Docker稳定版仓库

```shell
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

### 添加仓库后，更新apt源索引

```shell
sudo apt-get update
```

### 安装最新版Docker

```shell
sudo apt-get install docker-ce
```

### 用户权限修正

```shell
sudo usermod -a -G docker $USER
```

### 重启docker

```shell
systemctl restart docker
```

查看镜像信息

```shell
docker inspect xxx
```

## Docker命令

### 启动docker

```shell
systemctl start docker
```

### 关闭docker

```shell
systemctl stop docker
```

### 重启docker

```shell
systemctl restart docker
```

### docker设置随服务启动而自启动

```java
systemctl enable docker
```

### 查看docker 运行状态

```shell
systemctl status docker
# 如果是在运行中 输入命令后 会看到绿色的active
```

### 查看docker 版本号信息

```shell
docker version
```

```shell
docker info
```











## Docker部署Oracle19c

### 1、搜索镜像

```
docker search oracle19c
```

### 2、下载镜像(十分慢)

```shell
docker pull heart/oracle19c
```

### 3、创建挂载文件

```shell
# 创建文件
sudo mkdir -p /oracle/oradata
# 授权，不授权会导致后面安装失败
sudo chmod 777 /oracle/oradata
```

### 4、实行

```shell
docker run -d  -p 1524:1521 -p 5502:5500 -e ORACLE_SID=ORCLCDB -e ORACLE_PDB=ORCLPDB1 -e ORACLE_PWD=sys@123456 -e ORACLE_EDITION=standard -e ORACLE_CHARACTERSET=AL32UTF8 -v /oracle/oradata:/opt/oracle/oradata --name orcl19c_03 heartu41/oracle19c


```

### 5、查看oracle是否安装成功

```shell
# 查看启动日志
docker logs -ft orcl19c_03
```









### 3、实行

```shell
docker run --network=host \
-e ORACLE_SID=orcl \
-e ORACLE_PDB=orclpdb1 \
-e ORACLE_PWD=sys@123456 \
-e ORACLE_EDITION=standard \
-e ORACLE_CHARACTERSET=AL32UTF8 \
-v /mydata/oracle/oradata:/opt/oracle/oradata \
-v /mydata/oracle/diag:/opt/oracle/diag \
--restart=always \
--name oracle \
heartu41/oracle19c

说明：这个过程需要执行拷贝过程，也是很慢的，请耐心等待！

```



## Docker部署MatterMost聊天服务器

### 1、搜索镜像

```
docker search mattermost
```

### 2、下载镜像

```shell
docker pull mattermost/mattermost-preview
```

### 3、实行

```shell
docker run --name mattermost-preview -d --publish 8065:8065 mattermost/mattermost-preview
```

## Docker部署GitLab

### 1、搜索镜像

```shell
docker search gitlab
```

### 2、下载镜像

```shell
docker pull gitlab/gitlab-ce
```

### 3、运行

开始运行GitLab镜像

```shell
docker run -d -p 8443:443 -p 8090:80 -p 8022:22 --restart always --name gitlab -v /usr/local/gitlab/etc:/etc/gitlab -v /usr/local/gitlab/log:/var/log/gitlab -v /usr/local/gitlab/data:/var/opt/gitlab --privileged=true gitlab/gitlab-ce
```

这里解释一下这串代码的情况，复制的话就复制上面的命令

```shell
docker run 
-d               #后台运行，全称：detach
-p 8443:443      #将容器内部端口向外映射
-p 8090:80       #将容器内80端口映射至宿主机8090端口，这是访问gitlab的端口
-p 8022:22       #将容器内22端口映射至宿主机8022端口，这是访问ssh的端口
--restart always #容器自启动
--name gitlab    #设置容器名称为gitlab
-v /usr/local/gitlab/etc:/etc/gitlab    #将容器/etc/gitlab目录挂载到宿主机/usr/local/gitlab/etc目录下，若宿主机内此目录不存在将会自动创建
-v /usr/local/gitlab/log:/var/log/gitlab    #与上面一样
-v /usr/local/gitlab/data:/var/opt/gitlab   #与上面一样
--privileged=true         #让容器获取宿主机root权限
twang2218/gitlab-ce-zh    #镜像的名称，这里也可以写镜像ID
```

### 4、查看Gitlab是否已经启动

```shell
// 添加-a 参数，把启动的，没有启动的都列出来
docker ps
```

### 5、配置Gitlab

#### （1）首先，先进入容器

```shell
docker exec -it gitlab bash
```

#### （2）修改gitlab.rb文件

```shell
# 先进入到gitlab目录
cd /etc/gitlab   
# 编辑gitlab.rb文件  
vim gitlab.rb

# 在gitlab创建项目时候http地址的host(不用添加端口)
external_url 'http://xx.xx.xx.xx'

# 配置ssh协议所使用的访问地址和端口
gitlab_rails['gitlab_ssh_host'] = '192.168.XX.XX' // 和上一个IP输入的一样
gitlab_rails['gitlab_shell_ssh_port'] = 8022 // 此端口是run时22端口映射的8022端口
:wq // 保存配置文件并退出
```

#### （3）配置gitlab.yml文件

```shell
# 文件路径 /opt/gitlab/embedded/service/gitlab-rails/config
# 先进入到config目录下
cd /opt/gitlab/embedded/service/gitlab-rails/config
# 打开编辑gitlab.yml文件
vim gitlab.yml
# 修改host 与上面.rb文件修改的一致
# 修改port 为8090
```

### 6、重启服务

```shell
# 此命令为容器内重启服务命令
gitlab-ctl restart
```

### 7、使用浏览器打开Gitlab

```shell
# 网址+端口
http://192.168.XX.XX:8090/

# 密码路径
 vim /etc/gitlab/initial_root_password
```

### 8、常用命令

```shell
//容器外停止
docker stop gitlab   // 这里的gitlab 就是我们上一步docker run 当中使用--name 配置的名字
//容器外重启
docker restart gitlab
//进入容器命令行
docker exec -it gitlab bash
//容器中应用配置，让修改后的配置生效
gitlab-ctl reconfigure
//容器中重启服务
gitlab-ctl restart
```

## Docker部署redmine

### 1、搜索镜像

```shell
docker search redmine

docker search mysql
```

### 2、下载镜像

```shell
docker pull docker.io/sameersbn/redmine

docker pull docker.io/sameersbn/postgresql
```

### 3、实行

```shell
docker run --name=postgresql-redmine -e TZ="Asia/Shanghai" -d --env='DB_NAME=redmine' --env='DB_USER=redmine' --env='DB_PASS=redmine,.1q' --restart=always --volume=/home/docker/data/redmine:/var/lib/postgresql sameersbn/postgresql

docker run --name=redmine -e TZ="Asia/Shanghai" -d --link=postgresql-redmine:postgresql --publish=10083:80 --env='REDMINE_PORT=10083' --restart=always --volume=/home/docker/data/redmine/redmine:/home/redmine/data sameersbn/redmine
```

## Docker部署jenkins

安装前请确保主机已安装jdk

### 1、拉取最新版本的jenkins镜像

```shell
docker pull jenkins/jenkins:latest
```

### 2、创建jenkins目录

```
mkdir -p /home/jenkins_home
```

### 3、运行jenkins并映射端口

```shell
docker run -u root -d --name jenkins_01 -p 9988:8080 -p 50000:50000 -v /home/jenkins_home:/var/jenkins_home jenkins/jenkins
```

### 4、查看密码

```shell
cat /var/jenkins_home/secrets/initialAdminPassword
```

## Docker部署SVN

### 1、搜索镜像

```shell
docker search svn
```

### 2、下载镜像

```shell
docker pull docker.io/garethflowers/svn-server
```

### 3、实行

```shell
docker run --restart always --name svn -d -v /home/svn/repo:/var/opt/svn -p 3690:3690 garethflowers/svn-server
```

### 4、配置

```shell
#进入容器
docker exec -it svn /bin/sh
#创建aaa仓库
svnadmin create aaa
#修改svn目录中的文件配置
vi svnserve.conf

anon-access = none             # 匿名用户不可读写，也可设置为只读 read
auth-access = write            # 授权用户可写
password-db = passwd           # 密码文件路径，相对于当前目录
authz-db = authz               # 访问控制文件
realm = /var/opt/svn/svn       # 认证命名空间，会在认证提示界面显示，并作为凭证缓存的关键字，可以写仓库名称比如svn

修改passwd、和authz文件，没有这两文件直接创建并修改: vi passwd 和 vi authz
passwd文件内容如下：
[users]
# harry = harryssecret
# sally = sallyssecret
admin = 123456

authz文件内容如下：
[groups]
owner = admin
[/]               # / 表示所有仓库
admin = rw        # 用户 admin 在所有仓库拥有读写权限
[svn:/]           # 表示以下用户在仓库 svn 的所有目录有相应权限
@owner = rw       # 表示 owner 组下的用户拥有读写权限
```







```
docker run -d  -p 1524:1521 -p 5502:5500 -e ORACLE_SID=ORCLCDB -e ORACLE_PDB=ORCLPDB1 -e ORACLE_PWD=sys@123456 -e ORACLE_EDITION=standard -e ORACLE_CHARACTERSET=AL32UTF8 -v /oracle/oradata:/opt/oracle/oradata --name orcl19c_03 heartu41/oracle19c
```
