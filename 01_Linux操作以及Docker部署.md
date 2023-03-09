# Linux操作まとめ

## 一、常用的Linux命令

### 创建操作

```bash
# 创建一个空目录
mkdir test1
# 创建权限为777的目录
mkdir -m 777 test1
# 递归创建多个目录
mkdir -p test2/test22
```

### 查看操作

```shell
# 查看当前Linux系统的版本的方法
cat /proc/version
# 查看端口号
netstat -tunlp | grep 8000
# 查找指定名字的文件夹
whereis xxxx
```

### 删除操作

```shell
# 找到gitlab文件夹并删除
find / -name gitlab | xargs rm -rf
# 删除文件
rm -r 文件名
# 删除文件夹
rm -rf 文件夹名
```

### 端口映射

```shell
ssh -fgN -L 22(新端口):ip:22(原端口) localhost
```

### 文件夹权限

```shell
#单个文件夹
chmod 777 文件夹名（/xxx/xx/xx/）
#文件夹及其子文件
chmod -R 777 文件夹名（/xxx/xx/xx/）
```

### 防火墙

```bash
# 查看防火墙状态
$  sudo ufw status
# Status: inactive------>未启用
```



### 安装vim

```shell
sudo apt-get install vim

# vim常用命令
w 保存 不退出   ：q! 强制退出不保存
wq 保存 退出   ： e! 放弃所有修改     ：q 退出
```

### 拷贝

```bash
#文件拷贝
#把当前一个文件copy到远程服务器上：
scp /home/x.txt root@192.168.1.1:/home/root

#文件夹拷贝 -r(递归)
#Linux到本机（Windows）
scp -r root@ip:/usr/home E:\test
#本机（Windows）到Linux
scp -r E:\test root@ip:/usr/home

#本地到Docker
docker cp 本地路径 容器id或者容器名:容器内路径
#Docker到本地
docker cp 容器id或者容器名:容器内路径 本地路径
```

### 安装Docker

```shell
# 获取软件最新源
sudo apt-get update
# 安装包允许apt通过HTTPS使用仓库安装依赖
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
# 添加Docker的官方GPG密钥
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
# 设置Docker稳定版仓库
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
# 添加仓库后，更新apt源索引
sudo apt-get update
# 安装最新版Docker
sudo apt-get install docker-ce
# 用户权限修正
sudo usermod -a -G docker $USER
# 重启docker
systemctl restart docker
# 查看镜像信息
docker inspect xxx
```

### 周期性执行指令Crontab

```bash
# 编辑crontab（root下执行）
$ crontab -e
# 在打开的编辑器中添加以下行
$ * * * * * /bin/sh /path/to/your/your.sh

# 在crontab中设置的执行时间应该符合特定的格式：分 时 日 月 周 命令。
# 分 - 0-59
# 时 - 0-23
# 日 - 1-31
# 月 - 1-12
# 周 - 0-7（0和7都表示星期日）  
# 注意：上面的一个星号可以用多个值替换，中间用（,）隔开即可。

# 查看定时任务列表
$ crontab -l
```



## 二、Docker命令

```shell
# 启动docker
systemctl start docker
# 关闭docker
systemctl stop docker
# 重启docker
systemctl restart docker
# docker设置随服务启动而自启动
systemctl enable docker
# 查看docker 运行状态
systemctl status docker  # 如果是在运行中 输入命令后 会看到绿色的active
# 查看docker 版本号信息
docker version
docker info
# 加载镜像
docker load -i xxx.tar
# 删除容器
docker rm xxx
# 删除镜像
docker rmi xxx
#将本地文件拷贝到Docker内
docker cp 本地文件路径 容器ID/容器名:容器内路径
#镜像备份
docker commit -p 镜像id 备份名
#导出到本地目录
docker save 备份名 -o /Users/用户名/Desktop/备份名.tar
# docker run中常用参数
--name 为容器创建名字
-i 表示运行容器
-e 指定环境变量，容器中可以使用该环境变量
-d 创建守护式容器，并且在后台运行（这种创建，不会直接进入容器，-i,-t方式可以直接进入容器）
-v 数据卷映射（前者是宿主机目录，后者是映射到宿主机上的目录），可以使用多个
-p 表示端口映射，前者是宿主机端口，后者是容器内的映射端口，可以使用多个-p做多个端口映射
# 进入容器
docker exec -it 容器名/id /bin/bash
```



## 三、SVN备份Shell

### １、Shell作成（svn_backup.sh）

说明： 备份到windows的共享目录中，打成tar.gz

```bash
#!/bin/sh

# Windowsシステムの情報設定
WIN_SHARE="//xxx.xx.xx.x/svnbackup2"
WIN_USER="xxxxxx"
WIN_PASS="xxxxxx"

# マウント情報の設定
MONT_SHARE="/mnt/svnbackup2"

# SVN庫の情報の設定
SVN_REPO="/usr/svn/RPGプロジェクト"

# バックアップのフォルダ名
BACKUP_DIR="/home/svnBackUp"

# バックアップのファイル名
BACKUP_FILE="svn_backup_$(date +%Y%m%d%H%M%S).tar.gz"

# CIFSマウント
sudo mount -t cifs $WIN_SHARE $MONT_SHARE -o username=$WIN_USER,password=$WIN_PASS

# バックアップのフォルダを作成する、存在している場合（-p）、スキップする
sudo mkdir -p $BACKUP_DIR

# svnをバックアップ
sudo svnadmin dump $SVN_REPO | gzip > $BACKUP_DIR/$BACKUP_FILE

# windowsとおなじ
sudo rsync -avz $BACKUP_DIR/$BACKUP_FILE $MONT_SHARE
# windows余計なバックアップを削除する
cd $MONT_SHARE
ls -1t svn_backup_* | tail -n +3 | xargs rm -f

# もともとのバックアップを削除する（最近の二つを保留するだけです）
cd $BACKUP_DIR
ls -1t svn_backup_* | tail -n +3 | xargs rm -f

sudo umount $MONT_SHARE
```

### ２、设置Crontab

```bash
# root下执行（初次可以指定打开方式，vim容易点儿）
$ crontab -e

# 每天凌晨4点自动执行备份Shell
0 4 * * * /bin/sh /home/svnBackUp/svn_backup.sh
```



## 四、Docker常用服务部署

### 部署Nexus

```shell
# 下载镜像
docker pull sonatype/nexus3
# 新建目录
mkdir /usr/local/nexus
# 修改权限
chmod 777 /usr/local/nexus
# nexus默认使用8081端口
docker run -d --restart=always -p 8081:8081 --name nexus -v /usr/local/nexus:/nexus-data sonatype/nexus3
# nexus密码
# 进入容器
docker exec -it nexus /bin/bash
# 进入/opt/sonatype/sonatype-work/sonatype-work/目录，找到admin.password文件，里面的内容就是密码
cat admin.password
# 安装完成后可访问管理平台：http://ip:8081
# 默认管理员用户名：admin 密码：admin123
```

### 部署Oracle19c

```shell
# 搜索镜像
docker search oracle19c
# 下载镜像(十分慢)
docker pull heart/oracle19c
# 创建挂载文件
# 创建文件
sudo mkdir -p /oracle/oradata
# 授权，不授权会导致后面安装失败
sudo chmod 777 /oracle/oradata
# 实行
docker run -d  -p 1524:1521 -p 5502:5500 -e ORACLE_SID=ORCLCDB -e ORACLE_PDB=ORCLPDB1 -e ORACLE_PWD=sys@123456 -e ORACLE_EDITION=standard -e ORACLE_CHARACTERSET=AL32UTF8 -v /oracle/oradata:/opt/oracle/oradata --name orcl19c_03 heartu41/oracle19c
# 查看oracle是否安装成功
# 查看启动日志
docker logs -ft orcl19c_03
# 进入容器设置密码
docker exec -it orcl19c_03 /bin/bash 
./setPassword.sh ytxcc123   # ytxcc123为设置密码，这里修改为自己的即可
# 设置PDB
show pdbs;
alter session set container=ORCLPDB1;
# 创建用户
create user enterprise identified by 123456;
GRANT CONNECT, RESOURCE, DBA TO enterprise;
grant create session to enterprise;
grant connect,resource to enterprise;

# 查询所有用户
SELECT * FROM ALL_USERS;

# 连接
账号：enterprise
密码：123456
端口：1521
服务名称：ORCLPDB1DB1
```

### 部署MatterMost聊天服务器

```shell
# 搜索镜像
docker search mattermost
# 下载镜像
docker pull mattermost/mattermost-preview
# 实行
docker run --name mattermost-preview -d --publish 8065:8065 mattermost/mattermost-preview
```

### 部署GitLab

```shell
# 搜索镜像
docker search gitlab
# 下载镜像
docker pull gitlab/gitlab-ce
# 运行
docker run -d -p 8443:443 -p 8090:80 -p 8022:22 --restart always --name gitlab -v /usr/local/gitlab/etc:/etc/gitlab -v /usr/local/gitlab/log:/var/log/gitlab -v /usr/local/gitlab/data:/var/opt/gitlab --privileged=true gitlab/gitlab-ce
# 这里解释一下这串代码的情况，复制的话就复制上面的命令
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

# 查看Gitlab是否已经启动
# 添加-a 参数，把启动的，没有启动的都列出来
docker ps

# 配置Gitlab
# 首先，先进入容器
docker exec -it gitlab bash
# 修改gitlab.rb文件
# 先进入到gitlab目录
cd /etc/gitlab   
# 编辑gitlab.rb文件  
vim gitlab.rb
# 在gitlab创建项目时候http地址的host(不用添加端口)
external_url 'http://xx.xx.xx.xx'
# 配置ssh协议所使用的访问地址和端口
gitlab_rails['gitlab_ssh_host'] = '192.168.XX.XX' # 和上一个IP输入的一样
gitlab_rails['gitlab_shell_ssh_port'] = 8022 # 此端口是run时22端口映射的8022端口
:wq # 保存配置文件并退出
# 配置gitlab.yml文件
# 文件路径 /opt/gitlab/embedded/service/gitlab-rails/config
# 先进入到config目录下
cd /opt/gitlab/embedded/service/gitlab-rails/config
# 打开编辑gitlab.yml文件
vim gitlab.yml
# 修改host 与上面.rb文件修改的一致
# 修改port 为8090
# 此命令为容器内重启服务命令
gitlab-ctl restart
# 网址+端口
http://192.168.XX.XX:8090/
# 密码路径
vim /etc/gitlab/initial_root_password

# 容器外停止
docker stop gitlab   # 这里的gitlab 就是我们上一步docker run 当中使用--name 配置的名字
# 容器外重启
docker restart gitlab
# 进入容器命令行
docker exec -it gitlab bash
# 容器中应用配置，让修改后的配置生效
gitlab-ctl reconfigure
# 容器中重启服务
gitlab-ctl restart
```

### 部署redmine

```shell
# 搜索镜像
docker search redmine
docker search mysql
# 下载镜像
docker pull docker.io/sameersbn/redmine
docker pull docker.io/sameersbn/postgresql
# 实行
docker run --name=postgresql-redmine -e TZ="Asia/Shanghai" -d --env='DB_NAME=redmine' --env='DB_USER=redmine' --env='DB_PASS=redmine,.1q' --restart=always --volume=/home/docker/data/redmine:/var/lib/postgresql sameersbn/postgresql
docker run --name=redmine -e TZ="Asia/Shanghai" -d --link=postgresql-redmine:postgresql --publish=10083:80 --env='REDMINE_PORT=10083' --restart=always --volume=/home/docker/data/redmine/redmine:/home/redmine/data sameersbn/redmine
```

### 部署jenkins

```shell
# 拉取最新版本的jenkins镜像
docker pull jenkins/jenkins:latest
# 创建jenkins目录
mkdir -p /home/jenkins_home
# 运行jenkins并映射端口
docker run -u root -d --name jenkins_01 -p 9988:8080 -p 50000:50000 -v /home/jenkins_home:/var/jenkins_home jenkins/jenkins
# 查看密码
cat /var/jenkins_home/secrets/initialAdminPassword
```

### 部署SVN

```shell
# 搜索镜像
docker search svn
# 下载镜像
docker pull docker.io/garethflowers/svn-server
# 实行
docker run --restart always --name svn -d -v /home/svn/repo:/var/opt/svn -p 3690:3690 garethflowers/svn-server
# 配置
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

### 部署Postgres

```shell
# 搜索镜像
docker search postgres
# 下载镜像
docker pull postgres
# 实行
docker run -d --name postgres --restart always -e POSTGRES_USER='postgres' -e POSTGRES_PASSWORD='abc123' -e ALLOW_IP_RANGE=0.0.0.0/0 -v /home/postgres/data:/var/lib/postgresql -p 5432:5432 -t postgres
# 更新软件源列表
apt-get update 
# 安装vim
apt-get -y install vim
# 切换到目录/var/lib/postgresql/data
cd /var/lib/postgresql/data
# 修改：在所有IP地址上监听，从而允许远程连接到数据库服务器：
listening_address: '*'

# 客户端连接
#DB名:postgres
# 用户名：postgres
# 密码：postgres

# 修改编码格式（未实行）
update pg_database set encoding = pg_char_to_encoding('UTF8') where datname = 'basemap'
# 登录数据库
psql -U postgres -W
# 创建用户
create user admin with password 'admin';
# 创建DB
create database batteri owner admin;
# 授权(将全部权限授予用户admin)
grant all privileges on database batteri to admin;

# 说明：
# 将整个数据库的增删改查权限授予用户
grant select,insert,update,delete on database admin to readonly;
```
