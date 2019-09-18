## **1.购买腾讯云服务器并登录**

**1.1 购买腾讯云服务器**

<img src="./image/1.png" style="zoom:50%;" />

**1.2 购买成功**

<img src="./image/2.png" style="zoom: 70%;" />

**1.3 使用Web Shell登录已购买的云服务器实例**

<img src="./image/3.png" style="zoom: 75%;" />

**1.4 由于电脑已经拥有类似于x shell的final shell 于是我使用final shell登录腾讯云实例，首先新建连接**

<img src="./image/4.png" style="zoom: 60%;" />

<img src="./image/5.png" style="zoom: 75%;" />

**1.5 登录**

<img src="./image/6.png" style="zoom: 76%;" />



## **2.创建GitHub项目并在本地同步**

**2.1 注册GitHub账号**

**2.2 下载[**Git**](https://git-scm.com/downloads)安装并打开Git Bash，创建秘钥**

验证是否存在ssh keys

```
ls -al ~/.ssh
```

如果不存在ssh密钥，新建ssh key

```
ssh-keygen -t rsa -b 4096 -C “your_email@example.com”
```

**注意：**your_email@example.com替换成你的Github邮箱地址

直接回车保持默认，接下来继续回车，直到密钥创建成功

密钥地址默认存在C:\Users\your  name\\.ssh

打开公钥id_rsa.pub并复制内容到GitHub网站的Settings–>SSH and GPG keys的Key中

<img src="./image/8.png" style="zoom: 75%;" />

测试SSH Key是否配置成功

```
ssh -T git@github.com
```

**2.4 配置GitHub用户名和邮箱**

配置用户名

```
git config --global user.name “your name”
```

**注意：**"your name"替换成你的GitHub用户名。

配置邮箱

```
git config --global user.email “email@example.com”
```

**注意：**这里"email@example.com"替换成你的GitHub邮箱。



**2.5 创建GitHub项目并在本地进行同步**

在GitHub创建新的代码仓库

![](./image/9.png)

**注意：**填写仓库的名称“Repository name”，添加描述“Description”，还可以添加README（此处先不添加，后续采用命令行操作），以及添加忽略文件和开源协议。

首先在本地规划好一处文件夹用于同步GitHub的项目，然后打开Git Bash，定位到此次你想要同步的GitHub项目的文件夹，使用“cd”命令。

<img src="./image/10.png" style="zoom:120%;" />

初始化本地文件夹作为一个Git仓库：

```
git init
```

拷贝GitHub网站中的项目网址，并添加远程代码仓库的url：

```
git remote add origin “your url”
```

**注意：**your url替换成你的项目url。

验证是否成功

```
git remote -v
```

<img src="./image/11.png" style="zoom:104%;" />

新建README文档，README文档是每个GitHub项目必备，说明项目内容。上文没有创建，在此处完成：

```
touch README.md
```

添加文件夹中的所有文件

```
git add .
```

提交文件到项目仓库

```
git commit -m "your name"
```

**注意：**your name替换成你的项目名。

推送本地仓库更新至远程服务器

```
git push -u origin master
```

<img src="./image/12.png" style="zoom:104%;" />

**注意：**如果需要再次在本地更新，只需执行cd和最后三条命令。

## **3. 本地安装VMware Workstation和CentOS操作系统**

**3.1 下载VMware**

https://www.vmware.com/cn/products/workstation-player/workstation-player-evaluation.html

**3.2 下载centos镜像**

http://mirrors.aliyun.com/centos/7.6.1810/isos/x86_64/CentOS-7-x86_64-DVD-1810.iso

**3.3 安装Centos到VMware 上**

打开VMware选择新建虚拟机

<img src="./image/13.png" style="zoom:68%;" />

浏览到镜像存放的位置

<img src="./image/14.png" style="zoom:68%;" />

命名虚拟机分配磁盘空间

<img src="./image/15.png" style="zoom:68%;" />

<img src="./image/16.png" style="zoom:68%;" />

点击自定义硬件

<img src="./image/17.png" style="zoom:68%;" />

改成2g内存，分配2G内存

<img src="./image/18.png" style="zoom:68%;" />

打开虚拟机

<img src="./image/19.png" style="zoom:68%;" />

修改语言和时间

<img src="./image/20.png" style="zoom:68%;" />

<img src="./image/21.png" style="zoom:68%;" />

选择需要安装的软件

<img src="./image/22.png" style="zoom:68%;" />

<img src="./image/23.png" style="zoom:68%;" />

选择安装位置，在这里可以进行磁盘划分。

<img src="./image/24.png" style="zoom:68%;" />

<img src="./image/25.png" style="zoom:68%;" />

如下图所示，点击加号，选择/boot，给boot分区分200M。最后点击Add

<img src="./image/26.png" style="zoom:68%;" />

然后以同样的办法给其他三个区分配好空间后点击Done

<img src="./image/27.png" style="zoom:68%;" />

然后会弹出摘要信息，点击AcceptChanges(接受更改)

<img src="./image/28.png" style="zoom:68%;" />

设置主机名与网卡信息

<img src="./image/33.png" style="zoom:68%;" />

<img src="./image/34.png" style="zoom:43%;" />

设置root密码

<img src="./image/29.png" style="zoom:68%;" />

点击USER CREATION 创建管理员用户

<img src="./image/30.png" style="zoom:68%;" />

<img src="./image/31.png" style="zoom:68%;" />

安装完成进入centos

<img src="./image/35.png" style="zoom:54%;" />