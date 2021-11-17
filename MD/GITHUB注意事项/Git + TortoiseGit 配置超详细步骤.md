Git + TortoiseGit 配置超详细步骤

Git+TortoiseGit安装配置步骤

1. 先开通git账号，或者gitHub账号。

2. 下载git 。官网下载地址： https://git-scm.com/download/win 

3. 下载图形化界面管理工具TortoiseGit。Win7, Vista建议下载TortoiseGit-2.4.0.2 版本。

官网64位下载地址：https://download.tortoisegit.org/tgit/2.4.0.0/TortoiseGit-2.4.0.2-64bit.msi

中文语言包下载地址：

https://download.tortoisegit.org/tgit/2.4.0.0/TortoiseGit-LanguagePack-2.4.0.0-64bit-zh_CN.msi

4. 下载完毕后，将有三个文件如下图：



 

5. 安装git。双击打开”Git-2.14.0.2-64-bit.exe”全部默认选择，一直点击下一步，即可完成安装。



6. 安装界面化管理工具“TortoiseGit”。双击打开“TortoiseGit-2.4.0.2-64bit.msi”。全部默认选择，完成安装。

 

7. 安装“TortoiseGit”的中文语言包。双击打开“TortoiseGit-LanguagePack-2.4.0.0-64bit-zh_CN.msi”点击下一步即可完成安装。

8. 随便进入一个文件夹，鼠标右键进行设置。右键->TortoiseGit(T)->设置， 进入设置页面。

 

 

9. 在设置页面中，点击“常规设置”然后单击“重新运行首次启动向导”。

 

10. 在向导界面，所有选项一直下一步，直到下面界面，并按照界面选择。

 

11. 生成秘钥对，如下图操作：

 

12.  生成完的密钥界面如下。然后点击“Save private key”，将私钥保存在一个不常用的目录下，以保证不会被删除。名称随意，例如“c:\\xes.ppk”。然后将上面去榆中的密钥全部复制下来，备用。

 

13. 打开Git服务器个人页面，进入设置页面，按照下图添加密钥：

 

 

 

14. 确保git设置界面下面选项

 

 

 

 

 
————————————————
Git使用之基于SSH的Git服务器的客户端配置(下篇)

郎涯技术 2014-07-16 20:34:57  2547  收藏 1
分类专栏： # 软件工具 文章标签： git 服务器
版权

软件工具
专栏收录该内容
53 篇文章0 订阅
订阅专栏
1.  软件安装

Git-1.9.2-preview20140411

TortoiseGit-1.8.8.0-64bit.msi


1.1 安装msysgit

非常简单，基本就是一路下一步，有几个地方需要设置一下：






1.2 安装TortoiseGit



2.  私钥文件格式转换

putty的私钥文件格式和Copssh的不同，需要转换才能使用。TortoiseGit附带的Puttygen 密钥生成工具就可以完成转换。




点击 文件-Load Private Key，选择需要转换的密钥文件（原有的Copssh私钥ppk及对应的密码由管理员分发给大家，请大家在自己本机保存好私钥，私钥是访问git服务器的凭证）

再点击Save private key保存即可



3.  克隆仓库

需要通过URL ssh://<用户名>@192.168.2.111:22/SSH/home/<用户名>/仓库名 并使用之前生成的私钥文件private_key.ppk与密码才能访问。

新建一个文件夹，右键选择Git Clone。



然后在URL填入访问仓库的地址如: ssh://UIAdmin@192.168.2.111:22/SSH/home/UIAdmin/UICode，勾选Load Putty Key然后选择之前生成并经过转换的private_key.ppk,
点击OK，成功。


 
重要说明：

1. 先更新，再提交

 

2.  按最小功能（或是单功能）提交代码

每次提交以完成一项功能为宜，添加一个小特性或修复一个 bug 。

尽量不要按时间为基础，比如到下班的时候提交一次，不管这个功能是否完成。

在开发功能模块的时候，可以为每个小功能的测试通过后，进行提交一次。

我们提倡多提交，也就能多为代码添加上保险。

 

3. 不要提交未完成的代码

代码在提交之前，首先要确认自己已经检查无误。

项目经理在需要确保开发小组成员在签出代码之后能够在统一的环境中进行开发。

 

4. 每次提交必须书写明晰的注释

提交时可以使用一下方式，尽量说明你的代码实现了什么功能：

adda feature.

?xa bug.

removea feature.

尽量不要使用一下的方式, 这些方式没有说明你修改的代码实现什么功能：

addsome ?les

deletesome ?les

merge085bb3bc and a11bef06a

 

5. 提交时注意不要提交本地自动生成的文件,配置忽略配置文件

例如editplus 生成的 .bak ，Windows 生成的缩略图Thumbs.db  ，Smarty生成

的templates_c 文件夹中的缓存文件等等。

 

6. 不要提交自己不明白的代码, 需要看懂以后写上注释

 

7 不要放入与代码无关的文件

版本控制系统主要是管理代码的有序更新，方便程序员能够在发现错误的时候，回到

出现错误以前。所以与代码无关的文件尽量不要放进来，如编辑器软件，非项目本人的开发

文档，非文本格式的文档，上传的图片或文件。


4.  常见问题
1、ls不能显示中文目录 

解决办法：在git/etc/git-completion.bash中增加一行： alias ls='ls --show-control-chars--color=auto'

 

2、git commit不能提交中文注释 

解决办法：修改git/etc/inputrc中对应的行： set output-meta on set convert-metaoff 

 

3、git log无法显示中文注释 

解决办法：在git/etc/profile中增加一行： export LESSCHARSET=iso8859
————————————————

