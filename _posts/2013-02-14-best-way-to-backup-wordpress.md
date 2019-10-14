---
id: 1150
title: 备份WordPress的最佳的方式
date: 2013-02-14T20:23:02+08:00
author: chonghua
layout: post
guid: http://hechonghua.com/?p=1150
permalink: /best-way-to-backup-wordpress/
categories:
  - wordpress技巧
tags:
  - 备份
  - 数据安全
---
我们都应该知道,搞网站的都应该养成定期备份数据的好习惯,对于我们的WordPress来说也不例外,当然WordPress的备份,在于两个方面,你的主题、插件和修改过的文件，以及最主要的数据库文件，备份的方式也是多种多样，你可以手工备份后下载，也可以使用插件自动备份。

<!--more-->

对于懒人来说，自动备份当然是最佳选择，但是重华并不建议使用自动备份的插件:

1.不是所有的主机都可以支持自动备份然后发送到你的邮箱；

2.插件不是完全可靠，随时可能罢工；

最稳妥的还是手工备份,你可以使用FTP来下载网站文件,但是那个速度,你恐怕就没那个耐心了,假使你把博客配图也存储在主机上,那么FTP会让你想死的心都有。如果你的主机有Cpanel或者DA控制面板,那么就非常方便,直接在控制面板中就可以直接下载网站的文件和数据库,速度绝对和FTP不是一个数量级.

Cpanel的备份界面

<img style="display: block; float: none; margin-left: auto; margin-right: auto" src="http://chonghua-1251666171.cos.ap-shanghai.myqcloud.com/wpbackup_zpse5278699.png" width="520" height="476" alt="备份WordPress的最佳的方式" /> 

DA的备份界面

<img style="display: block; float: none; margin-left: auto; margin-right: auto" src="http://chonghua-1251666171.cos.ap-shanghai.myqcloud.com/wpbackup1_zps319e3e2b.png" width="520" height="354" alt="备份WordPress的最佳的方式" /> 

可以看出,其实控制面板的备份功能还是很强大的,可以选择需要备份的内容,一次性下载。也可以在同一界面进行备份文件的恢复工作。比起你直接在phpMyAdmin备份导入要方便和稳妥的多了。

如果你不想备份,其实还有一种保险的方式,那就是对文件的修改和文章的发布都在本地进行.

1.如果你需要修改主题或者插件的代码,可以先在本地修改好以后再上传到主机,而不要直接在主机上修改,这样万一你的修改出错,可以直接恢复本地的文件上传覆盖即可;

2.使用类似Windows live writer的离线发布工具,即使你的主机的所有文章都丢失,你的本地还有一份完整的文章备份,随时可以重新发布。

对于WordPress数据的安全，你还有什么更好的建议呢，不妨和大家分享一下。