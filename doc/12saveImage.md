## docker save image

- docker image save --help

  -o, --output string Write to a file, instead of STDOUT

- docker image save -o react-app.tar react-app:3

tar 类似 windows 的 zip file 压缩后的 体积更小

## 根据 tar load image

- docker image load -i react-app.tar

- docker images 查看 是否 load 成功
