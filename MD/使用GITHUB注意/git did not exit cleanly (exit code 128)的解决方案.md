git did not exit cleanly (exit code 128)的解决方案

蓝斯 2013-03-14 10:27:09  88335  已收藏 3
分类专栏： android
版权

android
专栏收录该内容
100 篇文章0 订阅
订阅专栏
最近在捣鼓github，想上传些代码上去，可是不知怎么滴push一直失败（以前可以）

提示说 git did not exit cleanly (exit code 128)

估计是哪里配置被我搞乱了

有问题自然找百度谷歌，可是试了很多方法终究不行

后来回到家里，重装了下TortoiseGit和msysgit

经过一番尝试，终于又可以了，隧写下此文以做小记

 

关于git的安装和基本配置就不在这里详细描述了，大家可以看这篇博文：

http://blog.csdn.net/geniuseoe2012/article/details/8534422

 

 

值得一提的是，在Network ---> SSH Client 里的配置是以下路径，如图所示：

 

 

在git clone 的时候复制SSH地址，不要搞错到Git Read-Only那个地址

在clone的时候要勾选Load Putty Key并选中私钥



之后的操作按正常流程走就行了，最后再push更改

有时候会提示说branch不同步之类的，具体错误信息里会说明，先pull一下再push就可以了

 对于提示一些网络超时之类的错误多试几次就Ok了

 

 

遇到 git did not exit cleanly (exit code 128)的错误原因有很多种

LZ的这种方案采用ssh链接地址（非只读地址），并通过私钥认证身份来同步更新

之前也有想过是只读git地址的问题，但当时ssh链接地址连clone都无法完成，才遭至后面乱七八糟的问题

总之以后大家遇到此类问题不妨着此方法一试，（最好把公私钥重新设置一遍）希望对大家有所帮助

 
————————————————
版权声明：本文为CSDN博主「蓝斯」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/lancees/article/details/8671637/
