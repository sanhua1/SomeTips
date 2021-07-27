### Git全局配置

以下两条命令配置全局变量

`git config --global user.name "yourName"`

`git config --global user.email "your_email@example.com"`

### Git密钥配置

1. 生成SSH

`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

一路回车，遇到y/n一律y

1. 查看SSH

`cat ~/.ssh/id_rsa.pub`

> 能看到密钥是rsa开头，邮箱结尾的

把生产的pub ssh密钥填到github或者gitlab的ssh设置里就ok了


### 一些基础git命令

1. git clone

`cd xxxx`
> xxxx是文件夹目录，用来进入到你希望clone到的文件夹

`git clone xxxx`
> xxxx是要clone的工程的ssh链接

1. git push

`git add .`

`git commit -am "备注"`

`git pull`

`git push`


> git pull其实可有可无，但是加上它是好习惯
