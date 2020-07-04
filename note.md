### git命令
- git init     //=>创建工具
- git add
- git add .
- git commit -m      //=>提交到暂存区
- git log        //=>查看历史版本记录
- git reflog     //=>查看所有历史版本
- git status     //=>查看状态
- git reset --hard+版本号      //=>回退


#### git和github
> GIT-HUB :https://www.github.com
一个网站(一个开源的源代码管理平台),用户注册后，可以在自己的账户下，创建仓库。用来管理项目的源代码(源代码基git创建到仓库中)
我们所熟知的插件、类库、框架等都在这个平台上有托管，我们可以下载观看和研究源码等

1.settings 用户设置
- profile 修改自己的基本信息
- Account Change username  修改用户名 个人页网址改变
- Security 可以修改密码
- Emails 修改邮箱

### 创建仓库
new respository 
name :英文加数字
- public 公共仓库作为开源的项目
- private 私有仓库作为内部团队协作管理的项目

2.code 查看历史版本信息


### 把本地仓库信息提交到远程仓库
> // 建立本地仓库和远程仓库的链接
 -$ git remote -v 查看链接
 让本地仓库和远程仓库新建一个链接 origin是随便起的一个连接名，(可以改成自己想要的名字),
 -$ git remote add origin [git仓库地址]
 删除关联信息
 $ git remote rm origin 

> 提交之前最好先拉取
 - $ git pull origin master
 把本地代码提交到远程仓库(需要输入github的用户密码信息)
 - $ git push origin master
 - $ git clone [远程仓库git地址][别名:可以不设置，默认是仓库名]

 ```
  真实项目开发流程:
    -1.组长或者负责人，先把中央仓库创建好。
    -2.小组成员基于git克隆 $git clone 把远程仓库及默认内容克隆到本地一份4
    (解决了三个事情:初始化一个本地仓库“git init”、和相应的远程仓库也把持了关联“git remote add”、把远程仓库默认内容拉取到本地“git init ”)
    -3.每个组员写完自己的程序后，基于“git add/git commmit”把自己修改的内容存放到历史区，然后通过“git pull/push”把本地信息和远程仓库信息保持同步即可(可能涉及冲突的处理)
    -4.增加协作者
```
### npm的基础操作
>  NPM node package manger :Node 模块管理工具,根据NPM我们可快速安装，卸载所需要的资源文件(例如：jquery、vu额、vue-router)

去NODE官网:https://nodejs.org/zh-cn/下载node,npm也就跟着安装了
- $ node -v
- $ npm -v 出现版本号，说明安装成功

#### 基于npm进行模块管理
https://www.npmjs.com/基于npm是从npmjs.com平台上下载安装
- $ npm install xxx 把模块安装在当前项目中(node_modules)
- $ npm install xxx -g 把模块安装在全局环境中
- $ npm i xxx@1.0.0 安装指定版本号的模块
- $ npm view xxx version > xxx.version.json 查看某个模块的版本信息(输出到指定json文件中)

```
  什么情况下会把模板安装在全局？
 -> 可以使用命令对任何项目进行操作
 -> 通过 $ npm root -g 查看全局安装的目录
 -> 因为在安装目录下生成了 xxx.cmd的文件，所以我们能够使用xxx命令进行操作的
 
 安装在本地项目中的模块
 -> 可以在项目中导入进来使用
 -> 但是默认不能基于命令来操作(因为没有.cmd文件)
 -> 但是可以基于package.json中的scripts,配置一些npm可以执行的命令，配置通过 $ npm run xxx 执行


```
- $ npm init -y 初始化当前项目的配置依赖清单(项目文件夹的名字不能出现中文、大写字母和特殊符号）
> =>创建成功后，在当前项目中生成package.json的清单文件
    dependencies:生产依赖模块(开发和项目部署的时候都需要)
    devDependencies:开发依赖模块(只有开发的时候需要)
    scripts:配置本地可执行命令的


- $ npm i xxx --save 把模块保存在清单生长依赖中
- $ npm i xxx --save-dev  把模块保存在清单开发依赖中
- $ npm install 跑环境，按照清单安装所需的模快

- $ npm root -g 查看全局模块的目录
- $ npm uninstall xxx      
- $ npm uninstall xxx -g  卸载安装过的模块

### window操作系统: 在某个文件夹下执行DOS命令
1、window+r  ->运行窗口中输入cmd
- > 磁盘符: 进入指定磁盘
- > cd xx 进入指定的目录
- > cd 直接拖进想要进入的目录文件夹

2.在文件夹地址栏直接输入cmd即可
3.在文件夹中shift+鼠标右键 -> 在此处打开命令窗口


如果想查看当前目录中的文件内容，
- mac: ls  /ls -A
- window : dir 

把less编译成css文件的命令 lessc 1.less 1.min.css -x