## linux下如何安装go环境

</br>

更新时间：2023-2-23

常说的go就是golang的简称，演示一下go语言的安装

官网：https://go.dev/

备用官网：https://golang.google.cn/

![](https://ghproxy.com/https://raw.githubusercontent.com/Yiov/notes/main/go/go-01.png)


## 开始安装

点击 `Download` 进入下载页面：https://go.dev/dl/

点击linux获取下载链接，比如我的

```
https://dl.google.com/go/go1.20.1.linux-amd64.tar.gz
```

![](https://ghproxy.com/https://raw.githubusercontent.com/Yiov/notes/main/go/go-02.png)


打开Xshell工具登录服务器，下载go

```bash
#下载
cd /www/server && wget https://golang.google.cn/dl/go1.20.1.linux-amd64.tar.gz

#解压
tar -xzvf go1.20.1.linux-amd64.tar.gz
```

![](https://ghproxy.com/https://raw.githubusercontent.com/Yiov/notes/main/go/go-03.png)


```bash
#添加环境变量
vi /etc/profile
```
![](https://ghproxy.com/https://raw.githubusercontent.com/Yiov/notes/main/go/go-04.png)


输入 `i` 进入编辑模式，方向键拉倒最底部，回车一下粘贴下面变量

```
export GOROOT=/www/server/go
export GOBIN=$GOROOT/bin
export GOPKG=$GOROOT/pkg/tool/linux_amd64
export GOARCH=amd64
export GOOS=linux
export GOPATH=/www/wwwroot/Golang
export PATH=$PATH:$GOBIN:$GOPKG:$GOPATH/bin
```

![](https://ghproxy.com/https://raw.githubusercontent.com/Yiov/notes/main/go/go-05.png)


按`ESC`退出编辑模式，输入`:wq` 回车保存并退出

> 额外说明：不保存退出 `:q!`

![](https://ghproxy.com/https://raw.githubusercontent.com/Yiov/notes/main/go/go-06.png)


环境变量生效命令

```
source /etc/profile
```
![](https://ghproxy.com/https://raw.githubusercontent.com/Yiov/notes/main/go/go-07.png)

检查版本

```
go version
```

![](https://ghproxy.com/https://raw.githubusercontent.com/Yiov/notes/main/go/go-08.png)


## 常见问题

### 1.如何卸载go

```bash
#查看goroot目录地址
go env

#根据目录路径删除即可
cd
rm -rf /www/server/go
```