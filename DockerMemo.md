#Docker 记录

##安装
* 必要条件
1. 64位
2. Linux虚拟机 内核3.11以上

* 步骤 （Ubuntu 16.04）

1. 安装相关包

    	sudo apt-get install apt-transport-https ca-certificates

		sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 -- recv-keys 58118E89F3A912897C070ADBF76221572C52609D


2. 编辑docker.list
		sudo vi /etc/apt/sources.list.d/docker.list
Ubuntu Xenial 16.04 (LTS)时如下添加一行
		deb https://apt.dockerproject.org/repo ubuntu-xenial main

3. 安装
		sudo apt-get update
		sudo apt-get install docker-engine
4. 启动		
        sudo service docker start
		sudo docker run hello-world

--追加dockerGroup
--如果没有组的好追加
sudo groupadd docker
--将用户添加到组
sudo usermod -aG docker tson1
--测试
docker run hello-world
--版本
docker --version
--
sudo docker info

-----------------------------------------------------------------
--镜像取得
docker pull ubuntu:16.04

--启动ubuntu16.04 image
docker run -it ubuntu:16.04

--镜像List
docker images
--镜像修改履历
docker ps -a

--delete all container
docker rm $(docker ps -a -q)
--

docker commit 57c312bbaad1 huangyong/javaweb:0.1
------------------------------------Dockerfile------------------test
docker build -t tson/java8 .



-----------------
RUN mkdir -p /usr/tomcat7/_appLogs/snt/
COPY . /usr/src/app
RUN chmod 777 /usr/tomcat7/_appLogs/snt/
EXPOSE 8080

/etc/init.d/tomcat7 start

export JAVA_HOME=/usr/local/jdk	

![][1]
[1]: http://latex.codecogs.com/gif.latex?\prod%20\(n_{i}\)+1



