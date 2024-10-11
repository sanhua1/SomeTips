## Git全局配置

以下两条命令配置全局变量

`git config --global user.name "yourName"`

`git config --global user.email "your_email@example.com"`  



<br>



## Git密钥配置

* 生成SSH

`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

一路回车，遇到y/n一律y

* 查看SSH

`cat ~/.ssh/id_rsa.pub`

> 能看到密钥是ssh-rsa开头，邮箱结尾的

把生成的pub ssh密钥填到github或者gitlab的ssh设置里就ok了  



<br>



## Git基础命令

* git clone

`cd xxxx`
> xxxx是文件夹目录，用来进入到你希望clone到的文件夹

`git clone xxxx`
> xxxx是要clone的工程的ssh链接

* git push

`git add .`

`git commit -am "备注"`

`git pull`

`git push`


> 在git push的时候，git pull其实可有可无，但是加上它是好习惯

* git pull

> 用于拉取线上仓库的数据，和clone不一样，clone是完整clone一个新的，git pull是用来同步本地和云端，云端的内容发生改变后，让本地的内容和云端一样

`git pull`

