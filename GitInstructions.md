# Git Instructions:
## Git Configuration
- git config --global user.name "small25300" (small25300为github用户名)
- git config --global user.email "small25300@163.com" (为github的注册邮箱)
- 配置其他文本编辑器在git bash直接调用：
	- 在git安装文件路径："D:\Program Files\Git\mingw64\bin"下创建一个文本文件，不带后缀名，名称最好是能简单代表你的文本编辑器，如vim
	- 在该文件中输入：
	```
	#!/bin/sh
	"D:\Editplus\editplus.exe" $1 &
	```
	- 保存好以后，直接在git bash中可以如此方法使用，例如：editplus E:/Git/instructions.md，如果该路径下没有该文件，则会在该路径下创建该文件，然后进入editplus的编辑界面。
- 配置与github远程连接：
	- ssh-keygen -t rsa -C "small25300@163.com" (为github注册邮箱)，运行后（注意运行过程中要求输入密码，可以为空）会在计算机用户下，如C:\Users\Administrator下生成一个.ssh文件夹，有3个文件：id_rsa、id_rsa.pub、known_hosts,然后用任意文本编辑器打开id_rsa.pub文件，复制所有内容，然后打开github网站，在用户头像右侧下拉菜单中选择setting->SSH and GPG keys->New SSH key,然后任意输入名称，在粘贴进刚才复制的文本内容。
- 常用基本配置完成。
## 如何在windows中添加.gitignore文件，忽略不用提交的文件:
- windows不能直接命名没有文件名只有后缀名的文件，创建方法如下：
	- 创建gitignore.txt文件(任意后缀名文件都可以)，然后在git bash中进入该文件所在目录，使用命令"rm gitignore.txt .gitignore"，则成功转为.gitignore文件。
	- 或者直接在gitignore.txt文件夹内，右键使用Git Bash Here（注意：不是在gitignore.txt文件上，而是该文件所在文件夹的空白位置）
	- 用任意文本编辑器打开.gitignore文件，出入要忽视的文件类型即可，如：
	```
	# Editplus ignore file class
	*.*.bak %表示对如file.md.bak类型的文件忽略
	```