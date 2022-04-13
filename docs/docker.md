## Docker安装文档

### 1. Overall

服务器部署依赖于Docker和Docker-compose
我们保证部署可以在以下版本软件正常运行
| APP | DOCKER  | DOCKER-COMPOSE |
|:---:|:-------:|:--------------:|
| VER |   1.9+  |      1.2+      |

### 2. 安装Docker 

#### 2.1 使用包管理软件

如果您使用Mac系统而且安装过包管理软件可以使用以下指令
```sh
$ brew install --cask docker-ce
```

如果是UbuntuOS 请使用
```sh 
$ sudo apt-get update
$ sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
$ echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

#### 2.2 官方文档(推荐)

您可以按照此教程安装[Docker安装教程](https://docs.docker.com/get-docker/)

### 3. 安装Docker-Compose

#### 3.1 使用pip

请使用如下指令安装
```sh
$ pip3 install docker-compose 
```

#### 3.2 官方文档（推荐）

您可以按照此教程安装[Docker-Compose安装教程](https://docs.docker.com/compose/install/)


