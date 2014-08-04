---
layout: post
title:《如果描述缺陷？》example
category: blog
description: 
---

##缺陷例子： iPhone的相册中分享一张照片到新浪微博上，由于网络链接断掉微博发送失败，但原来写的微博文字部分内容却没保存。

现在流行的缺陷库管理工具都可以设定必填项，一般包括：
- 缺陷标题 （Summary）
- 缺陷简单描述（description）
- 缺陷重现步骤（duplicate procedure）
- 缺陷类型 （defect type）
- 软件版本信息 （version)
- 优先级 （priority）
- 严重级别 （severity）
- 缺陷频率 （frequency）
- 测试环境：如软件语言，操作系统等等
- 缺陷提交者以及缺陷修改者等
- 其它注解（comments）
- 辅助信息（附件贴图，log信息等等）

我们在提交defect的时候最重要的描述就是
- 缺陷标题 （Summary）
- 缺陷简单描述（description）
- 缺陷重现步骤（duplicate procedure）

Summary, 在缺陷库中第一眼看到的是缺陷的标题，所以这个summary就要非常简洁明了而且能做到其他项目组成员可以不用看其它各种环境信息就知道这是什么缺陷。
description，有时候可以和summary相同，目的就是可以让其他项目组成员尤其是测试人员可以在不看到procedure的时候可以重现bug，描述的清楚的好处就是后面verify缺陷的时候，测试人员可以展开做测试，而不仅仅局限当前步骤。
procédure，这个就是上篇博文里写到的，这个记录尤其对一些sometimes，once的缺陷尤为重要，开发人员可以从步骤中所牵涉到的功能操作等分析问题所在。

回到上面，对于这个缺陷的我们如何描述呢？

Summary：After failed to share photo from iPhone's Photo Album to sina weibo, the text content already entered will be lost.
Description:  While iPhone's network(both Wi-Fi and 3G) is disconnected, try to share photo from photo album to Sina weibo, enter some texts and confirmed, which will be failed. the text content already entered will be lost.
Procedure:
Make sure iPhone's network is disconnected, including both Wi-Fi and 3G.
a, Enter "Photos" of iPhone built-in application-> select any a photo->Share
b, select Weibo
c, enter some texts and press "Send".
d, An error message will be prompted to tell users that cannot Send weibo,  user could only press OK to exit the dialog.
[Defect] the texts already entered is lost. 
[note1] it's not good experience for user that user could not find what they have entered.
[note2] I also checked in Settings of iPhone and Weibo iPhone client app, which also didn't save the failed weibo.
Environment: iPhone 4S(US) , iOS 6.0 beta.
Frequency：always
.......

其它信息可以依据当前项目要求设定。

当然了，以上各种描述各种要求都是弹性的，上面的缺陷描述的例子一般是在大项目尤其是大团队的时候特别重要。若是小团队尤其是开发和测试在一起的情况下，我们描述尽可能的简洁，可能只需要一个summary就可以让开发人员知道缺陷并且很快修改缺陷了。规则都是人定的，一般在团队作战的时候有规则会让沟通更畅通，但一个测试的时候，各种规则往往可能是牵绊，因为事情太多，我们就要寻找更简单的办法。



[Angelia]:    http://angeliaw.github.com  "Angelia"