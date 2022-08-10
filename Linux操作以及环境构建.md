# Linux操作まとめ

## 常用的Linux命令

###  查看当前Linux系统的版本的方法

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

### 查找操作

```shell
whereis xxxx
```





## 安装Docker











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


