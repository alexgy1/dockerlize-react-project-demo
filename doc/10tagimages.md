## helpful when you rollback or upgrade

build image `docker build -t react-demo-app .`


加一个版本号 :1 之类的 
`docker build -t react-demo-app:1  . `

## remove tag 
`docker image remove + tagname`

- `docker image remove react-demo-app:1 `


## 给已有的新增一个tag
`docker image tag react-demo-app:latest react-demo-app:100 `

`docker images  ` 查看结果


## latest并不总是代表最新的版本 

```diff
+ react-demo-app                   101       5e4096a609cc   6 seconds ago    289MB
react-demo-app                   100       8f04fa2415b5   6 minutes ago    289MB
react-demo-app                   latest    8f04fa2415b5   6 minutes ago    289MB
```

## 如何latest保证最新的？ 
- 重新根据image id build一个最新的
`docker image tag 5e4 react-demo-app:latest`


```diff
react-demo-app                   101       5e4096a609cc   2 minutes ago    289MB
+react-demo-app                   latest    5e4096a609cc   2 minutes ago    289MB
react-demo-app                   100       8f04fa2415b5   9 minutes ago    289MB
```