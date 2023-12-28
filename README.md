# PrePre

# 有关git的相关基础操作（学习）

一、git的安装

1.进行安装，这里不再进行赘述，可以点击下面的网站进行安装：
https://blog.csdn.net/mukes/article/details/115693833

2.设置右键 git bash here

移植版Git或者通过[VS安装](https://so.csdn.net/so/search?q=VS安装&spm=1001.2101.3001.7020)不在右键菜单的，这个时候需要自己设置：

　　1.通过在“运行”中输入‘[regedit](https://so.csdn.net/so/search?q=regedit&spm=1001.2101.3001.7020)’，打开注册表。

　　2.找到[HKEY_CLASSES_ROOT\Directory\Background]。

　　3.在[Background]下如果没有[shell],则右键-新建项[shell]。

　　4.在[shell]下右键-新建项[open in Git ],其值为“Git Bash Here",此为右键菜单显示名称。

　　5.在[open in Git]下右键-新建-字符串值[Icon],双击编辑，其值为“D:\...\Git\mingw64\share\git\git-for-windows.ico”。此为菜单加图标。本步不是必须。

　    6.在[open in git]下右键-新建-项[command],其值为 "D:\Program Files\Git\git-bash.exe" 。

二、git在本地仓库的相关操作

1.创建一个仓库(初始化仓库)

git init

最好创建在你的项目文件夹里面

![Create_git](C:\Users\86139\Desktop\Create_git.png)

2.查看仓库状态

git status

![Infromation_git](C:\Users\86139\Desktop\Infromation_git.png)

3.向暂存区中添加文件

git add

首先你需要在你的项目文件夹里添加你的文件（C，txt，md...）
![add_git](C:\Users\86139\Desktop\add_git.png)

4.保存仓库的历史记录

(1)git commit -m ""

-m 参数后的 "First commit"称作提交信息，是对这个提交的 概述。

git commit命令可以将当前暂存区中的文件实际保存到仓库的历 史记录中。通过这些记录，咱们就可以在工作树中复原文件



![commit_git](C:\Users\86139\Desktop\commit_git.png)

(2)记述详细提交信息

直接执行 git commit命令

在编辑器中记述提交信息的格式如下。

第一行：用一行文字简述提交的更改内容 

第二行：空行 ●

第三行以后：记述更改的原因和详细内容 只要按照上面的格式输入，今后便可以通过确认日志的命令或工具 看到这些记录。 

在以 # 标为注释的 Changes to be committed（要提交的更改）栏中，可以查看本次提交中包含的文件。将提交信息按格式记述完毕后，记得保存并关闭编辑器（如果直接关闭，会中断commit），以 #（井号）标为注释的行不必删 除。随后，刚才记述的提交信息就会被提交。

5.查看提交日志

git log

git log命令可以查看以往仓库中提交的日志。包括可以查看什么人在什么时候进行了提交或合并，以及操作前后有怎样的差别。关于合并我们会在后面解说（maybe）

![log_git](C:\Users\86139\Desktop\log_git.png)

三、将本地git仓库传入远程仓库（github）

1.进行链接 git与github

通过ssh协议

可以先在c盘中查看自己是否又.ssh文件

若有则跳过第三步

在git界面输入：

（1）git config --global user.name "注册名"

（2）git config --global user.email "注册邮箱"

（3）ssh-keygen -t rsa -C "自己的邮箱"  // 生成ssh

![Create_ssh](C:\Users\86139\Desktop\Create_ssh.png)

2.github配置ssh

打开.ssh中的id_rsa.pub文件，全选，复制全文

github->账户->setting->SSH and GPG keys->new SSH key

将复制的内容填入key中

![github_ssh_02](C:\Users\86139\Desktop\github_ssh_02.png)



![github_ssh_03](C:\Users\86139\Desktop\github_ssh_03.png)

测试ssh链接，输入下面的代码

ssh -T git@github.com

![ssh_connect](C:\Users\86139\Desktop\ssh_connect.png)

3.将本地内容上传到github中（建议方法）

（1）在github中先创建一个仓库，记得不要创建README.md文件

（2）将仓库下载至本地

（3）在相应文件夹中进行项目的编写

（4）上传文件

![ssh](C:\Users\86139\Desktop\ssh.png)

