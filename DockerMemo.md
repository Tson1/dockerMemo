#Docker 记录
[TOC]
##安装
* 必要条件
1. 64位
2. Linux虚拟机 内核3.11以上

* 步骤 （Ubuntu 16.04）

1. 安装相关包
```
sudo apt-get install apt-transport-https ca-certificates
sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 -- recv-keys 58118E89F3A912897C070ADBF76221572C52609D
```

2. 编辑docker.list
` sudo vi /etc/apt/sources.list.d/docker.list`

 Ubuntu Xenial 16.04 (LTS)时如下添加一行
` deb https://apt.dockerproject.org/repo ubuntu-xenial main`

3. 安装Docker
		sudo apt-get update
		sudo apt-get install docker-engine
4. 启动Docker
        sudo service docker start
		sudo docker run hello-world

5. 追加dockerGroup
+ 如果没有组的好追加
`sudo groupadd docker`

+ 将用户添加到组
`sudo usermod -aG docker tson1`

+ 测试
`docker run hello-world`

+ 版本确认
```
docker --version
sudo docker info
```
***
##应用篇
###基本
1. 镜像取得
`docker pull ubuntu:16.04`

2. 启动ubuntu16.04 image
`
docker run -it ubuntu:16.04
`

3. 镜像List
`docker images`

4. 镜像修改履历
'docker ps -a'

5. delete all container
`docker rm $(docker ps -a -q)`

5. 1. delete all image 
docker rmi $(docker images -q --filter "dangling=true")

6. commit container to image by none
`docker commit 57c312bbaad1 huangyong/javaweb:0.1`

###构建Dockerfile
1. 构建命令
`docker build -t tson/java8 .`



* * *

#### メモ書き
-----------------
RUN mkdir -p /usr/tomcat7/_appLogs/snt/
COPY . /usr/src/app
RUN chmod 777 /usr/tomcat7/_appLogs/snt/
EXPOSE 8080

/etc/init.d/tomcat7 start

export JAVA_HOME=/usr/local/jdk

./usr/lib/jvm/java-8-oracle/jre/bin/java

/var/lib/tomcat7/logs/catalina.out

/usr/lib/jvm/java-7-oracle/jre/bin/java

/usr/lib/jvm/java-1.7.0-openjdk-amd64


![][1]
[1]: http://latex.codecogs.com/gif.latex?\prod%20\(n_{i}\)+1



