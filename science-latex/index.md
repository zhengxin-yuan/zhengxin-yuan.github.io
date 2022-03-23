# LaTeX安装

<!--more-->
{{< admonition abstract>}}
LaTeX安装
{{< /admonition>}}

## 0. 前言
**LaTeX**（音译“拉泰赫”）是一种基于 ΤΕΧ 的**排版系统**，由美国计算机学家莱斯利·兰伯特 （Leslie Lamport） 在20世纪80年代初期开发，利用这种格式，即使使用者没有排版和程序设计的知识也可以充分发挥由 TeX 所提供的强大功能，能在几天，甚至几小时内生成很多具有书籍质量的印刷品。对于生成复杂表格和数学公式，这一点表现得尤为突出。因此它非常适用于生成高印刷质量的科技和数学类文档。**这个系统同样适用于生成从简单的信件到完整书籍的所有其他种类的文档**。（参考资料：[百度百科](https://baike.baidu.com/item/LaTeX/1212106?fr=aladdin)）

___

## 1. TeX Live 安装

**TeX Live** 是由国际 TeX 用户组织 TUG 开发的 TeX 系统，它是**运行 LaTeX 代码所必须的环境**，支持不同的操作系统平台。其 Windows 版本又称 fpTeX，Unix/Linux 版本即著名的 teTeX（参考资料：[CTeX](http://www.ctex.org/TeXLive)）。

### 步骤一：推荐先安装 TeX Live 2019

下载链接：[TeX Live 2019](http://tug.org/texlive/)。按照下图步骤，下载相应版本：
{{< image src="/images/Science/Latex/Latex_01.png" caption="Fig. 1. TeX Live 2019 下载 A" width="100%" >}}
{{< image src="/images/Science/Latex/Latex_02.png" caption="Fig. 2. TeX Live 2019 下载 B" width="100%" >}}

下载完成后正常安装，选择自己喜欢的安装路径，安装过程如图所示：
{{< image src="/images/Science/Latex/Latex_03.png" caption="Fig. 3. TeX Live 安装中" width="56%" >}}
安装完成后会正常提示，也可以用 cmd 检查电脑是否成功安装 LaTeX 环境。

### 步骤二：配置镜像源
打开 Tex Live Manager，如图所示配置源：
{{< image src="/images/Science/Latex/Latex_04.png" caption="Fig. 4. 配置镜像源" width="93%" >}}
推荐使用重大版本。至此，TeX Live 的安装就结束了。以上内容参考资料：[简书ACC839303568](https://www.jianshu.com/p/6df6e6da82b1)

___

## 2. TeXstudio 编译器
**TeXstudio** 是一款编译器，也就是方便你敲代码的软件，集成一些代码。

### 步骤三：推荐安装编译器 TeXstudio
下载链接：[TeXstudio](http://texstudio.sourceforge.net/)

按照下图步骤，下载相应版本：
{{< image src="/images/Science/Latex/Latex_05.png" caption="Fig. 5. TeXstudio 下载" width="95%" >}}

### 步骤四：配置编译器 TeXstudio
进行如下配置，使用 XeTeX 进行编译
{{< image src="/images/Science/Latex/Latex_06.png" caption="Fig. 6. 配置编译器 TeXstudio" width="95%" >}}

至此，在你的电脑上已经可以使用 LaTeX 对论文进行排版了。关于后续深入地学习，需要读者自行查阅资料。

___

## 3. 参考资料
* [Latex: TexStudio的使用](https://blog.csdn.net/pipisorry/article/details/54565608)
* [LaTeX使用介绍——基于Tex Live2018](https://www.jianshu.com/p/6df6e6da82b1)
* [Elsevier 期刊 Latex 投稿模板](https://blog.csdn.net/yaoxiaochuang/article/details/52167661)

___

## 4. 推荐模版
硕士论文模版：[清华大学](https://github.com/xueruini/thuthesis); [中国科学技术大学](https://github.com/ustctug/ustcthesis); [重庆大学](https://github.com/nanmu42/CQUThesis)。

___

## 5. 推荐书籍
LaTeX入门_刘海洋

