# 达梦数据库ARM版镜像
达梦数据库ARM版8.0容器部署方案
## docker安装
### CentOS
`yum install -y docker`  
`systemctl start docker #启动docker daemon`  
`systemctl enable docker #设置docker daemon开机运行`
## 单机部署
### 快速启动
`docker run -p 5236:5236 toyangdon/dm:8-arm64`
### 持久化数据
`docker run -v /dm:/home/dmdba/data -p 5236:5236 toyangdon/dm:8-arm64`
### 后台开机自动运行
`docker run -v /dm:/home/dmdba/data -p 5236:5236 -d --restart always toyangdon/dm:8-arm64`
### 默认用户名/密码
`SYSDBA/SYSDBA`
### disql 工具
`docker run --rm -it --entrypoint="/home/dmdba/dmdbms/tool/disql" toyangdon/dm:8-arm64`  
示例  
`SQL> connect SYSDBA/SYSDBA@{{server_ip}}:5236`
## 集群部署
//TO_DO
## 镜像构建
`docker build -t toyangdon/dm:8-arm64 .`
