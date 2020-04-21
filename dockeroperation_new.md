## docker的常用操作笔记

***
从docker hub上拉取自定义的镜像  
docker pull happykala/build_env
***
依托存在的镜像重新命名一个tag值  
docker tag oldname newname:xxx   
替换上面xxx的值可以为新的命名镜像创建一个新的tag值
***
删除指定的镜像  
docker rmi xxx  
xxx替换为需要删除的镜像的repository的值  
***
基于镜像来创建容器  
docker run -itd xxx  
xxx替换为需要删除的镜像的repository的值
***
查看运行中的容器  
docker ps
***
基于正在运行的容器创建镜像  
1.查看当前正在运行的容器  
docker ps  
2.找到需要创建进行的容器进入其中  
docker exec -it #contrainer_id# bash  
以bash的方式进入id为#contrainer_id#的容器内部  
3.使用ctrl+d的方式退出容器  
4.创建镜像  
docker commit -m "#des#" -a "#author#" #contrainerid# #newname#  

|字段|描述|示例值|
|:----:|:----:|:----:|
|#des#|镜像的注释说明|---|
|#author#|镜像的作者|---|
|#contrainerid#|容器的id|---|
|#newname#|新创建镜像的名称|---|


http server location upstream

***
查看正在运行的容器  
docker ps  
查看所有的容器信息  
docker ps -a  
删除容器  
docker rm #container_id# 将#continer_id#替换为要删除的容器即可  
启动容器  
docker start #container_id#  
停止容器  
dokcer stop #container_id#


基于镜像创建容器并指定端口映射


docker run -i -t -p 8088:80 happykala/build_env:port   /bin/bash



