## Server部署文档

#### 1. Overall

完整的服务器部署包含如下三个不同的部分

| 部署MYSQL | 部署FLASK | 部署NGINX |
|:-----:|:-----:|:-----:|


#### 1. 下载

请使用如下指令下载部署仓库
```
$ git clone git@github.com:JHU-EN650-631-01-SP22-G01/dockers.git dockers
```

当您完成下载后请进入对于路径
```bash 
$ cd docker
```


#### 2. 部署MYSQL(可选)

##### 2.1 默认部署

您可以使用以下指令启动MYSQL

```bash 
docker-compose up -d mysql
```

##### 2.1 自定义部署

当mysql成功运行后您需要给mysql服务器的root账户分配远程访问权限, 请使用如下指令进入mysql服务器client
```sh
$ docker exec -it deployment_flask_1 sh
```
当加入mysql container后, 可以直接运行mysql client 然后分配权限, 请使用以下指令进入mysql client

```sh
$ mysql -uroot -p12345
```

当进入mysql client后请输入如下指令分配远程访问权限

```sql
GRANT all privileges ON *.* TO 'root'@'%';
```

当执行完成后使用如下指令退出 mysql客户端
```sh
$ exit
```
然后使用再次使用此指令退出docker container
```sh
$ exit
```

请使用以下指令检查是否成功运行mysql服务器

```sh
$ docker ps 
```

如果成功将会看到一个名为`deployment_mysql_1`的容器

#### 3. 部署Flask

##### 3.1 默认部署

直接使用以下指令部署 Flask
```bash 
docker-compose up -d flask
```
请使用以下指令检查是否成功运行 flask 服务器

```sh
$ docker ps 
```

如果成功将会看到一个名为`deployment_flask_1`的容器

##### 3.2 自定义部署

Section4.1 为配置默认配置，使用main branch中的代码进行部署。 如果需要修改不同的branch请设置环境变量`GIT_BRANCH`, 您可以使用如下指令： 
```sh
$ export GIT_BRANCH=???
```

#### 5. 部署apache（在开发过程中暂时不需要）

直接使用以下指令部署 Apache
```bash 
docker-compose up -d apache
```
请使用以下指令检查是否成功运行 apache 服务器

```sh
$ docker ps 
```

如果成功将会看到一个名为`deployment_apache_1`的容器
