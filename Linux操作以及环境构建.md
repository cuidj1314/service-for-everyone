# Linux操作まとめ

 查看当前Linux系统的版本的方法

```shell
cat /proc/version 
```

mattermost

```shell
docker run --name mattermost-preview -d --publish 8065:8065 mattermost/mattermost-preview
```

docker

要更新 Mattermost 预览图像和容器，必须首先通过运行以下命令来停止并删除现有的 **Mattermost 预览**容器

```shell
docker pull mattermost/mattermost-preview
docker stop mattermost-preview
docker rm mattermost-preview
```

mkdir gitlab

export GITLAB_HOME=/srv/gitlab

docker exec -it 容器名 /bin/bash

```shell
docker-compose up -d
```

rm -rf $GITLAB_HOME

netstat -tunlp | grep 80

sudo curl -L https://get.daocloud.io/docker/compose/releases/download/1.25.1/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

docker exec -it gitlab-ce grep 'Password:' /etc/gitlab/initial_root_password

sudo gitlab-ctl reconfigure

三、Docker搭建Gitlab

## 1、获取镜像

```shell
docker pull gitlab/gitlab-ce
```

## 2、运行

开始运行Docker镜像

```shell
docker run -d -p 8443:443 -p 8090:80 -p 8022:22 --restart always --name gitlab -v /usr/local/gitlab/etc:/etc/gitlab -v /usr/local/gitlab/log:/var/log/gitlab -v /usr/local/gitlab/data:/var/opt/gitlab --privileged=true gitlab/gitlab-ce
```

```shell
docker run -d -p 8443:443 -p 8090:80 -p 8022:22 --restart always --name gitlab -v /home/gitlab/config:/etc/gitlab -v /home/gitlab/logs:/var/log/gitlab -v /home/gitlab/data:/var/opt/gitlab --privileged=true gitlab/gitlab-ce
```

## 3、配置Gitlab

1.首先，先进入容器

```shell
docker exec -it gitlab bash
```

[(1条消息) Docker中安装Gitlab详细全教程_连小黑的博客-CSDN博客_docker安装gitlab](https://blog.csdn.net/lianxiaohei/article/details/122665812)

尝试 gitlab-ctl reconfigure 、gitlab-ctl restart

查看端口号

```
netstat -tunlp | grep 8000
```

[如何使用 Docker Compose 安装 GitLab？ (czerniga.it)](https://www.czerniga.it/2021/11/14/how-to-install-gitlab-using-docker-compose/)

完全删除

```shell
find / -name gitlab | xargs rm -rf
```

```shell
# docker-compose.yml
version: '3.6'
services:
  web:
    image: 'gitlab/gitlab-ce:latest'
    restart: always
    hostname: 'gitlab-sub'
    container_name: gitlab-ce
    environment:
      GITLAB_OMNIBUS_CONFIG: |
        external_url = 'http://172.16.73.183:10080'
        gitlab_rails['gitlab_shell_ssh_port'] = 8022
    ports:
      - '10080:80'
      - '10443:443'
      - '1022:22'
    volumes:
      - '$GITLAB_HOME/config:/etc/gitlab'
      - '$GITLAB_HOME/logs:/var/log/gitlab'
      - '$GITLAB_HOME/data:/var/opt/gitlab'
    shm_size: '256m'
```

//容器外停止
docker stopgitlab // 这里的gitlab 就是我们上一步docker run 当中使用--name 配置的名字
//容器外重启
docker restart gitlab
//进入容器命令行
docker exec -it gitlab bash
//容器中应用配置，让修改后的配置生效
gitlab-ctl reconfigure
//容器中重启服务
gitlab-ctl restart
