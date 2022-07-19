## login dockerhub

> 需要付费的 docker 账号
> docker image tag imageId codewithalex/react-app:2

docker login
username
Password

docker push codewithalex/react-app:2

## change some file make another build and push

docker build -t react-app:3

加上统一的名字
docker image tag react-app:3 codewithalex/react-app:3  
登陆过 就可以直接 push 了
docker push codewithalex/react-app:3
