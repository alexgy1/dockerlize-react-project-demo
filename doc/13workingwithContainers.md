## starting & stop containers

- docker ps 查看正在运行的 container

#### 指定后台运行 -d

- docker run -d react-demo-app

### 指定 container 名字

- docker run -d --name blue-sky react-demo-app

## publishing ports

- -p localhost port : containerport
- docker run -d -p80:3000 --name blue-sky c1

## Viewing logs

- docker logs --help
- docker logs + container id
- `docker logs 58b7d`

-f Follow log output

- `docker logs -f 58b7d `
- `docker logs -n 5 58b7d ` 查看日志的最后五行 日志比较长的时候 有用

- `docker logs -n 5 -t 58b7d ` -t 加时间输出

## Executing commands in containers

- docker run : start a new container and run in command
- docker exec : execute command ina running container

起一个 名字为 c1 的 本地 8888 端口

`docker run -d -p8888:3000 --name c1 react-demo-app`

这样本地访问 localhost:8888 就可以访问到了

- docker exec c1 ls 查看目录

也可以执行 shell

- docker exec -it c1 sh

exit 退出 shell

## stop container

- docker stop + name

`docker stop c1`

## start container

- docker start c1
- start vs run
- start start a stoped container
- run run a new one

## Removing containers

- docker rm c1

对一个正在运行的 container
想要移除 有两种方式
方式 1:
停止 并且移除

方式 2 ：
强制移除
`docker rm -f c1`
docker ps 查看是否移除成功

只看想要的 container 使用｜

docker ps -a | grep c1

# 停止全部 container

- docker container prune

## Persisting data using volumes

- 每个 container 有自己文件系统
  验证

- docker exec -it 58b sh
- echo data > data.txt 写入一个文件
- exit 退出

再进入到另一个容器中

- docker exec -it a3f sh
- ls | grep data 发现查不到
- exit

使用 volume 存储文件

## Sharing source code with containers
