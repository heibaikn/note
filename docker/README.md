# docker

## 安装docker

- [安装请戳这里](https://yeasy.gitbooks.io/docker_practice/install/mac.html)

## docker基本命令

```
docker --help  帮助命令
docker search 查找镜像 
docker pull 安装镜像
docker images 镜像列表
docker run [OPTIONS] IMAGE [COMMAND] [ARG...] 创建一个新容器
         --name 容器名称 -p 端口指定  -restart 是否自动重启  -e 环境变量
docker ps 查看激活容器

docker container COMMAND Name 容器操作 
      ls 容器列表 start 开始 stop 停止 exec 进入容器
```

## docker-compose
使用docker-compose 对多个容器容器操作，首先创建docker-compose.yml文件
```yml
# Use root/example as user/password credentials
version: '3.1'
services:
  mongo:
    image: mongo
    restart: always
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: example

  mongo-express:
    image: mongo-express
    restart: always
    ports:
      - 8081:8081
    environment:
      ME_CONFIG_MONGODB_ADMINUSERNAME: root
      ME_CONFIG_MONGODB_ADMINPASSWORD: example
```
```
docker-compose COMMAND 批量处理容器
      up 创建和开始容器 
      down 停止和删除容器
```

## Dockerfile
- 获取镜像 [dockerhup](https://hub.docker.com/)

当镜像无法直接满足需求时，我们就需要定制这些镜像。首先创建Dockerfile文件

```Dockerfile
FROM node:8
EXPOSE 3000
WORKDIR /app
COPY package.json index.js ./
RUN npm install
CMD ["npm", "start"]
```
> 运行 docker build -t node-self .
```
docker build [OPTIONS] PATH | URL | - 构建自定义镜像
docker image history IMAGENAME 查看镜像历史

```
