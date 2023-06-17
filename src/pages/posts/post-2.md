---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Astro博客开发'
tags: ["博客开发"]
pubDate: 2022-07-01

---
# （一）配置开发环境_Astro搭建静态博客

## 一、搭建静态博客的框架选择

​	2022年出的Astro框架据说是效率最高的，因此，选择了Astro框架进行搭建。

## 二、配置环境的搭建

​	配置环境需要的工具包括：[VS code](https://az764295.vo.msecnd.net/stable/ee2b180d582a7f601fa6ecfdad8d9fd269ab1884/VSCodeUserSetup-x64-1.76.2.exe), [Node.js]([Node.js (nodejs.org)](https://nodejs.org/en)), Github，Astro, Git。

## 三、 创建Astro项目

​	在电脑Terminal终端中，通过Node.js包管理工具==npm==来创建一个新的Astro项目。

```
npm create astro@latest
 “Would you like to install dependencies?” type y
 if you plan on writing TypeScript, type n
 Would you like to initialize a new git repository?” type y.
```

## 四、在VS code中打开Astro项目

	1. 找到刚才创建的Astro项目的路径，在VS code中==打开该项目==
	
	2. 打开VS code的命令终端（快捷键：==Ctrl + J==），开始调用Astro开发者服务
	
	```
	#在VS code的终端输入下面代码
	npm run dev
	
	#会出现下面的代码
	> dsktop-blog@0.0.1 dev
	> astro dev
	   astro  v2.1.8 started in 41ms
	  ┃ Local    http://localhost:3000/
	  ┃ Network  use --host to expose
	```
	
	3. 打开对话框中的==Local网址==，关闭Local网址（快捷键：Ctrl + C）

## 五、在Astro中输入第一行文字

1. 在VS code中打开stro项目。
2. 在文件导航中找到index.astro文件==src/pages/index.astro==，并打开。

![](（一）配置开发环境_Astro静态博客.assets/image-20230330101346482.png)

​	3. 在<h1>标题中写下你的第一句话<h1>

## 六、在VS code中配置Git的相关信息

 	下载[Git]([Git - Downloading Package (git-scm.com)](https://git-scm.com/download/win))，并安装。Git能够将VS code 本地的代码传到Github中。
 	下载[Remote Repositories](https://code.visualstudio.com/)，并安装。Remote Repositories能够将Github中的代码下载到本地。
 	在VS code中配置Git的安装路径，==设置==>>搜索==git.path==![img](Astro搭建个人的静态博客.assets/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5ZSv5LiA55qE6Zi_6YeR,size_20,color_FFFFFF,t_70,g_se,x_16.png)

​	![](（一）配置开发环境_Astro静态博客.assets/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5ZSv5LiA55qE6Zi_6YeR,size_20,color_FFFFFF,t_70,g_se,x_16-16801836291232.png)

​		![](（一）配置开发环境_Astro静态博客.assets/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5ZSv5LiA55qE6Zi_6YeR,size_20,color_FFFFFF,t_70,g_se,x_16-16801836537194.png)

## 七、 Astro项目部署到Github上的方法。

​	**第一种方式**是在Github==新建==一个==repository==，将该repository克隆下来与Astro项目融合之后，再上传到Github中。

​	**第二种方式**也需要再Github上新建一个repository，直接将本地的Astro项目上传到该repository中。

​	**第三种方式**同样需要再Github上新建一个repository，然后在Github中的repository输入git代码，将本地文件直接传上来，不需要编辑器的参与。

​	<u>**三种方式各有优劣，但是必须要学会前两种**</u>。最重要的是第一种，大多数时候会从Github上直接克隆代码到本地的编辑器中进行调试。有的时候会用到第二种，自己在本地新建一些项目的时候需要将整个项目传到Github中去。

​	**三种方式中的共同点**：使用git操作的流程大致都相同，具体包括以下几个步骤：

​	（1）引入git工具对文件进行管理：`git init` 在文件夹中引入git进行管理，这个代码会在当前路径的文件夹中创建git管理必要的文件，例如其特有的版本管理目录等文件。

​	（2）向git工具管理的文件夹中添加文件：`git add *` 其中*号是指你要添加的文件名。 ` git add .`是指添加该路径下所有文件内容到git管理的文件中。

​	（3）确认向Github提交的文件：` git commit -m "文件名"` 确认你将要向Github中上传的文件。

​	（4）Git与Github中的repository建立连接：` git remote add origin https://github.com/github_name/github_repository_name.git`注意最后仓库名后面要加==.git== 。

​	（5）Git与Github中的传输进行加密：首先，在==c盘用户目录==下寻找.shh目录，找到==id_rsa==与==id_rsa.pub==两个文件。如果没有这两个文件就看[这篇文章](https://cloud.tencent.com/developer/article/1504684#)。然后，在Github中增加SSH Key密钥：==Settings==>>==SSH and GPG KEYS==>>==New SSH Key==，将在刚才本地文件夹中复制==id_rsa.pub==里面的Key填到==New SSH Key==对话框中。最后在Githu中点击==Add SSH Key==，这就完成了加密。

​	（6）上传文件：`git push -u origin master` 由于第一次上传，远程仓库是空的，所以加上-u这个参数，远程有内容之后，下次只需要这样输入：`git push -u origin master`。

​	**<u>注意随时使用代码   ==git status==  随时查看仓库的状态</u>**	！！！[Git 的学习资料]([(40条消息) 视频同步笔记：狂神聊Git_狂神说的博客-CSDN博客](https://blog.csdn.net/qq_33369905/article/details/106647320))！！！！

## @@@阶段小成果@@@

1. 学会了Markdown的语法来编辑Markdown文档
2. 学会了Markdown文档一键上传多个平台的方法
3. 自主搭建了Typora+图片库+Picgo的免费开发环境
4. 学会了VS code与Github平台的便捷开发与上传方法
5. 自主搭建了 VS code+Github+Git 的O2O免费开发环境

