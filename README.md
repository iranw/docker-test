# docker 镜像使用

###### 1、安装docker环境
* http://dockerpool.com/static/books/docker_practice/install/centos.html
* http://dockerpool.com/static/books/docker_practice/install/ubuntu.html


###### 2、载入docker镜像
```
#docker load --input ubu64.tar
```

###### 3、查看docker镜像容器
```
#docker images
```
`注`：如果发现build:v3这个镜像容器 则说明引入成功

###### 4、启动容器
```
#docker run -idt -p 80:80 -p 9001:9001 -v /root/wwwroot/:/usr/local/nginx/html build:v3
```
`注`：
* a、做了本机80端口与容器80端口映射（业务环境）
* b、做了本机9001端口与容器9001端口映射（supervisor管理页面）
* c、做了本地地址(/root/wwwroot)与容器地址（/usr/local/nginx/html）的目录映射（只需在本地编写开发代码即可）

###### 5、查看启动状态
```
#docker ps
```
`注`：如果出现docker容器(build:v3)进程 则说明启动成功

###### 6、打开url
* http://ip
* http://ip:9001


`注`：
* 目前容器编译安装软件如下
 * nginx....../usr/local/nginx
 * php......../usr/local/php
 * supervisor
