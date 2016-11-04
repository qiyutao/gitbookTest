#Git仓库的建立
***
##Git的安装
- **1. 在Linux上安装**

  	在 Linux 上可以使用发行版包含的基础软件包管理工具来安装。 
  	
     * Fedora：
      `$ sudo yum install git`
     
     * Ubuntu：
  	`$ sudo apt-get install git`
  	
- **2.在 Mac 上安装**
	
	最简单的方法是安装 Xcode Command Line Tools。 Mavericks （10.9） 或更高版本的系统中，在 Terminal 里尝试首次运行 git 命令即可。 如果没有安装过命令行开发者工具，将会提示你安装。
	
- **3.在 Windows 上安装**
       
	  在 Windows 上安装 Git 有两种安装方法:
       
	* 官方版本可以在 Git 官方网站下载。 打开[ http://git-scm.com/download/win]( http://git-scm.com/download/win)，下载会自动开始。

	* 另一个简单的方法是安装 GitHub for Windows。 该安装程序包含图形化和命令行版本的 Git。

---
##Git的配置

*  **用户信息**
	
	当安装完 Git 应该做的第一件事就是设置你的用户名称与邮件地址。 这样做很重要，因为每一个 Git 的提交都会使用这些信息，并且它会写入到你的每一次提交中，不可更改：

	` $ git config --global user.name "XXX"`
	
	`$ git config --global user.email XXXXXX@XXX.com `
	
* **检查配置信息**

	如果想要检查你的配置，可以使用` git config --list ` 命令来列出所有 Git 当时能找到的配置。
	
		$ git config --list
	    	user.name=John Doe
	    	user.email=johndoe@example.com
	    	color.status=auto
	    	color.branch=auto
	    	color.interactive=auto
	    	color.diff=auto
	    	...
***
##获取 Git 仓库

	有两种取得 Git 项目仓库的方法。 第一种是在现有项目或目录下导入所有文件到 Git 中； 第二种是从一个服务器克隆一个现有的 Git 仓库。

* **1.在现有目录中初始化仓库**
	
	首先进入要创建Git仓库项目目录并输入：
	
	`$ git init`
	
	该命令将创建一个名为 .git 的子目录，这个子目录含有你初始化的 Git 仓库中所有的必须文件，这些文件是 Git 仓库的骨干。
	
	此时我们需要对项目中的文件进行跟踪，可通过`git add `命令来实现对指定文件的跟踪，然后执行` git commit` 提交：
	
	$ git add *.c
	
	$ git add LICENSE
	
	$ git commit -m 'initial project version'
    	
* **2.克隆现有的仓库**

	如果你想获取已经存在了的 Git 仓库，你可以执行` git clone` 命令，默认配置下远程 Git 仓库中的每一个文件的每一个版本都将被拉取下来。
	
	克隆仓库的命令格式是` git clone [url] `。 比如，要克隆 Git 的可链接库 libgit2，可以用下面的命令：

	`$ git clone https://github.com/libgit2/libgit2`
	
	这会在当前目录下创建一个名为 “libgit2” 的目录，并在这个目录下初始化一个 .git 文件夹，从远程仓库拉取下所有数据放入 .git 文件夹，然后从中读取最新版本的文件的拷贝。
	
    如果你想在克隆远程仓库的时候，自定义本地仓库的名字，你可以使用如下命令：
    
    `$ git clone https://github.com/libgit2/libgit2 mylibgit`
	
	这将执行与上一个命令相同的操作，不过在本地创建的仓库名字变为 mylibgit。
	
***
		
