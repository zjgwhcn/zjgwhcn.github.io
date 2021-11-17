一，安装GIT后，安装TortoiseGit。

二，然后右键找到TortoiseGit，下拉之Settings（其中两个坑）。

  坑一：找到Network 的SSH client：，设置为“C:\Program Files\TortoiseGit\bin\TortoiseGitPlink.exe”（关键是TortoiseGitPlink.exe）。

  坑二：找到GENERAL>Re  run First Start Wizard点开，一直点下一下，直到出现“GENERATE PUTTY KEY PAIT”点击其（在其左侧若有选择项切记选择openSSH我用的这个）,弹开选择"GEMERATE"点击,生成需要的密钥并在GITHUB你的服务器端设置(网上有设置教程,不再缀述！）

三，然后就可以使用GIT CLONE到本地了。

   坑一：在GITHUB服务端复制SSH地址，比如这样的“git@github.com:zjgwhcn/zjgwhcn.github.io.git”。然后使用GIT CLONE 克隆，不然将来上传的时候常出错。
   