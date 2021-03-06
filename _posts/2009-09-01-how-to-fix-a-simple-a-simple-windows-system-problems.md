---
id: 292
title: 如何简单的修复简单的windows系统问题
date: 2009-09-01T12:24:38+08:00
author: chonghua
layout: post
guid: http://hechonghua.com/how-to-fix-a-simple-a-simple-windows-system-problems/
permalink: /how-to-fix-a-simple-a-simple-windows-system-problems/
categories:
  - 其他资源
tags:
  - 系统修复
---
有时候,windows系统出现了小问题,但是有些是不需要动不动就重装系统的,也不需要请专门的维修人员来修的,或许几个简单的步骤,就可以快速的让你的系统恢复正常!下面就是一些简单的处理系统故障的方法,但是不要指望这些方法能修复所有的问题!其实我也早就想写一些这一类简单的处理方法,但既然有人写了,我就不重复劳动了!对应的故障引起原因,红色字体标出!

<!--more-->

&#160;&#160;&#160;&#160; 1、最后一次配置

Windows2000以上版本的操作系统，每次成功启动之后都会对系统注册表进行自动备份，一旦我们发现Windows系统本次不能正常启动时，那多半是我们上一次<font color="#ff0000">对系统进行了错误的操作或者对某些软件进行了错误的安装，从而破坏了系统注册表的相关设置</font>。此时，我们可以尝试使用上一次成功启动时的配置来重新启动一下计算机系统：只要在重新启动系统的过程中，及时按下F8功能键，调出系统启动菜单，然后选中“最后一次正确的配置”项目，这样的话Windows系统说不定又能启动正常了。

2、修复系统文件

如果Windows系统的某些核心文件不小心被损坏的话，那么即使使用“最后一次配置”，Windows系统也很难保证就能启动正常。如果Windows系统只是<font color="#ff0000">有少量的系统文件受损的话</font>，那我们不妨借助Windows系统内置的SFC扫描修复命令，来尝试对那些已经遭受破坏的系统文件进行修复，一旦修复成功后，那Windows系统的启动又会恢复正常状态了。在修复受损系统文件时，只要依次单击“开始”/“运行”命令，在弹出的系统运行对话框中，输入字符串命令“sfc/scannow”，单击回车键后，该命令程序就会对系统每个角落处的系统文件进行搜索扫描，一旦发现系统文件的版本不正确或者系统文件已经损坏的话，它就能自动弹出提示界面,<font color="#ff0000">要求我们插入Windows系统的安装光盘</font>，以便从中提取正常的系统文件来替代不正常的系统文件，从而达到修复系统文件的目的。要是系统修复操作成功的话，相信我们重新启动计算机系统时，就不会看到有什么不正常的现象了。

3、注销当前用户

如果Windows系统的受损部位只是<font color="#ff0000">由于安装了不恰当的软件，或者是对软件进行了不合适的设置</font>引起的话，那么我们通常可以通过“注销当前用户”的方法，来对受损的Windows系统进行急救，因为软件对系统设置的影响往往只能限于当前登录的用户，一旦在当前用户状态下系统不能正常运行的话，我们完全可以注销当前用户，并以其他的用户重新登录系统，这样Windows一般又能恢复正常运行状态了。

在注销当前用户、换用其他用户登录系统之前，我们需要先打开系统的控制面板窗口，然后双击其中的“用户帐户”项目，再单击其后界面中的“添加”按钮，来重新创建一个新的登录帐号，同时为该帐号设置一个合适的访问密码，并将对应的帐号设置为超级管理员权限。

由于换用其他帐号登录Windows系统后，保存在当前用户目录下的一些重要数据可能就访问不到了，为此在注销用户之前，我们有必要打开系统的资源管理器窗口，找到当前帐号所对应的用户目录，例如要是当前登录系统的帐号为aaaa的话，那么系统默认的帐号目录应该为“C:＼Windows＼DocumentsandSettings＼aaaa”，将该目录下面的一些重要数据全部备份到系统分区以外的其他分区目录中。

做好了上面的准备工作后，现在我们就能依次执行“开始”/“注销aaaa”命令，来将当前的登录帐号注销掉，然后重新用刚刚创建好的帐号登录Windows系统；在用新帐号成功登录进Windows系统后，我们再把前面备份好的重要数据恢复到当前帐号所对应的新用户目录下面，这样的话受损Windows系统就能恢复以前的正常运行状态了。

4、重注册DLL文件

Windows系统有时之所以会频繁受到损伤，主要是许多应用程序常常共享调用一些DLL文件，一旦有的应用程序在使用完毕被自动卸载掉后，这些应用程序所调用的DLL文件往往也会跟着被删除掉了，这么一来Windows系统或系统中的其他应用程序再次调用那些共享了的DLL文件时，就自然会发生错误现象了。

在急救那些由于<font color="#ff0000">系统DLL文件丢失</font>引起的Windows系统运行不正常故障时，我们根本不需要重新安装操作系统，只需要对那些已经丢失了的DLL文件进行一下重新注册，就能让系统恢复正常运行状态了。考虑到我们并不知道究竟是哪一个或哪几个DLL文件被损坏了或丢失了，我们不妨通过下面的方法，来对系统所有的DLL文件都重新注册一下，而不需要单独对某一个或某几个DLL文件进行注册：

首先打开类似记事本这样的文件编辑程序，然后在对应的程序界面中输入如下命令行代码：

@echooff

for%1in(%windir%＼system32＼*.dll)doregsvr32.exe/s%1

将上面的命令行代码保存成一个扩展名为BAT的批处理文件，例如这里笔者假设将该代码内容保存为了repair.bat文件；其次为repair.bat文件创建一个快捷图标，并将该快捷图标直接拖放到系统的桌面上，等到日后需要对系统中的所有DLL文件进行重新注册时，我们只需要双击repair.bat文件的快捷图标，系统就会自动开始对所有的DLL文件执行重新注册操作了。一旦所有DLL文件被重新注册过之后，此时我们不妨再尝试运行一下Windows系统，相信此时的系统肯定会十分正常了！

5、恢复原始文件

如果Windows系统不正常运行的故障是由于<font color="#ff0000">系统注册表被意外破坏引起</font>的话，那么我们完全可以借助常规的copy命令，来将系统原始的注册表信息直接复制到系统对应的目录下，这样可以快速地实现恢复受损系统文件的目的。由于Windows系统第一次被安装成功后，原始的注册表信息都会被自动备份保存到系统安装目录下面的Repair子目录中，因此我们只要将Repair子目录下面的注册表信息直接复制到系统的配置目录中就可以了：

如果本地计算机只安装了一个操作系统的话，那我们不妨借助Windows98启动光盘，来将系统先引导到DOS命令行状态；如果本地计算机中安装了两个以上操作系统的话，那只需要将系统切换另外一个能正常运行的系统中就可以了；接下来在DOS命令行状态，通过CD命令将当前目录切换到“%windir%＼Repair”子目录状态下，并依次执行如下字符串命令：

copysam%windir%＼system32＼config

copysystem%windir%＼system32＼config

copysoftware%windir%＼system32＼config

copydefault%windir%＼system32＼config

copysecurity%windir%＼system32＼config

一旦在执行上面的字符串命令过程中，系统弹出提示询问是否将以前的文件覆盖掉时，我们直接进行肯定回答就可以了。等到系统的注册表信息被所有原始注册表文件替换掉后，我们再次重新启动一下系统，相信此时系统肯定能正常运行了。

6、系统还原功能

要是我们的计算机中安装的是WindowsXP系统的话，那除了通过上面的方法来急救受损的系统外，还能借助WindowsXP系统特有的“<font color="#ff0000">系统还原功能</font>”，来将Windows系统的运行状态恢复到正常，下面就是该方法的具体实施步骤：

依次单击“开始”/“程序”/“附件”/“系统工具”/“系统还原”命令，在其后弹出的系统还原设置向导界面中，将“恢复我的计算机到一个较早的时间”项目选中，然后单击“下一步”按钮；在其后弹出的系统还原点列表窗口中，我们一般选择一个离当前时间比较近的一个还原点来还原系统，一旦选好目标还原点后，继续单击“下一步”按钮，Windows系统就能被自动恢复到以前的正常工作状态了。值得一提的是，在使用该功能之前，我们一定要在Windows系统运行正常的状态下，及时创建好合适的系统还原点，以便日后恢复系统时所用！

原文来自:[http://www.pc-course.cn/course/595.html](http://www.pc-course.cn/course/595.html "http://www.pc-course.cn/course/595.html")
