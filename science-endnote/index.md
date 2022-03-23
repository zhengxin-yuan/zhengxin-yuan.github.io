# EndNote中英文参考文献混排

<!--more-->
{{< admonition abstract>}}
通过文献管理软件EndNoteX9，实现中英文参考文献混排效果，帮助你轻松完成学位论文，毕业撒花！
{{< /admonition>}}

{{< admonition info "作者" false>}}
文章作者：阿杰（ shanjunjie19@163.com ）

技术指导：南神（ nan_bo_wen@163.com ）
{{< /admonition>}}

## 0. 前言
[EndNote](https://endnote.com/)是一款由SCI<font color="red">**官方开发**</font>的文献管理软件，具有强大的参考文献管理功能，支持<font color="blue">**众多国际期刊**</font>的文献格式，涵盖各个研究领域。

由于EndNote研发团队**只关心**英文文献的适配问题，使用EndNote来管理中文文献确实并非明智之举，其常会出现乱码、兼容性差等问题。

<font color="red">**但是**</font>，在撰写硕士、博士学位论文时，参考文献的中英文混排是不可避免的，这点总是让同学们感到非常苦恼。

阅读完本篇文章，<font color="blue">**妈妈再也不用担心我的参考文献中英文混排了**</font>，吃嘛嘛香，一口气上五楼不喘气！

___

## 1. 建立中文文献类型
### 步骤1
首先，进入 Endnote X9，在 Endnote 工具栏中选择【Edit】→【Preference ⋯】→【Reference Types】，在这里点开。

然后，在 **Journal Article** 下拉菜单里面，选择一个新的文献类型，并对其进行设置。新文献类型比如 "Unused1、2或者3" 都可，这里选择 Unused2 示范。
{{< image src="/images/Science/EndNote/EndNoteEC_01.png" caption="Fig. 1. 建立文献类型" width="80%" >}}

### 步骤2
随后，点击【Modify Reference Types】进行新格式设置，设置内容如下图所示，完成后点击确定。
{{< image src="/images/Science/EndNote/EndNoteEC_02.png" caption="Fig. 2. 取名中文文献类型" width="80%" >}}
___

## 2. 转换文献类型
### 步骤3
将 Endnote 文献库中，所有的中文文献的文献类型（Reference Type）都转换为刚刚定义的 Chinese Journal 类型，并且把 Author 中的内容复制到 Secondary Author 中，如下图所示。
{{< image src="/images/Science/EndNote/EndNoteEC_03.png" caption="Fig. 3. 转换文献类型" width="80%" >}}
___

## 3. 新建输出格式</h2>
### 步骤4&5
通过工具栏上的【Edit】→【Output Styles】→【New Style ⋯】进行新输入格式的设置，需要设置的位置如图所示（画红框的地方）。

在 About this Style 栏中【Category:】填 “Generic”，Anonymous Works、Page Numbers、Journal Names、Section 可以不变。
{{< image src="/images/Science/EndNote/EndNoteEC_04.png" caption="Fig. 4&5. 类型描述" width="80%" >}}


### 步骤6
对于中文期刊，引文在正文中的显示格式大都采用数字上标编号标注，Citations 的设置如下：Templates 输入框在 Insert Field 中选择 “Bibliography Number” 进行设置，前后加上中括号，设置为上标格式，最后如图显示。这样在正文中引用文献时则表示为文献出现的顺序号，格式为上标。Citations 的其余部分可以不变。
{{< image src="/images/Science/EndNote/EndNoteEC_06.png" caption="Fig. 6. 建立模板" width="80%" >}}


### 步骤7
中文期刊的参考文献格式可自行查阅 <a href="https://baike.baidu.com/item/%E5%8F%82%E8%80%83%E6%96%87%E7%8C%AE%E6%A0%87%E5%87%86%E6%A0%BC%E5%BC%8F/15571284?fr=aladdin">规范</a> 获得。

在 Reference Types 中选上 Journal Article 代表英文文献，通过 Insert Field 工具按钮将英文文献格式设置为：（输入的时候注意用英文输入法和注意哪有空格）
```Code
（制表符）Author. Title [J]. Journal, Year|, Volume|(Issue): Pages.
```
接着在 Reference Types 中选择 Chinese Journal 代表中文文献，点击 Insert Field 选择字段将中文文献格式设置成：
```Code
（制表符）Secondary Author. Title[J]. Journal, Year|, Volume|(Issue)|: Pages.
```
接着在 Reference Types 中选择 Conference Paper 代表会议文献，点击 Insert Field 选择字段将会议论文格式设置成：
```Code
（制表符）Author. Title[A]. Editor.Conference Name[C].Conference Location:Publisher,Year|:Pages.
```
接着在 Reference Types 中选择 Thesis 代表中文文献，点击 Insert Field 选择字段将学位论文格式设置成：
```Code
（制表符）Author. Title[D]. University, Year|.
```
接着在 Reference Types 中选择 Book 代表中文文献，点击 Insert Field 选择字段将专著格式设置成：
```Code
（制表符）Author. Title[M].Year.
```
如图所示。其中，制表符在右上角插入。
{{< image src="/images/Science/EndNote/EndNoteEC_07.png" caption="Fig. 7. 示例" width="100%" >}}


### 步骤8
英文作者设置，Author Lists 的设置代表英文文献格式，作者前后之间用“,”分隔，显示前 3 位作者，超过 3 个作者缩略为 “, et al. ”。如图所示。
{{< image src="/images/Science/EndNote/EndNoteEC_08.png" caption="Fig. 8. 英文作者设置" width="100%" >}}

### 步骤9
Editor Lists 的设置代表中文文献格式，作者前后之间用 “,” 分隔，显示前 3 位作者，超过3个作者缩略为 “, 等.” ，如图所示。
{{< image src="/images/Science/EndNote/EndNoteEC_09.png" caption="Fig. 9. 中文作者显示设置" width="100%" >}}


### 步骤10
最终参考文献序号和悬挂的设置， Layout 中的 Start each reference with 部分在 Insert Field 工具按钮中选择 “Bibliography Number” （与第五步的设置类似，只是不需要变成上标），前后加上中括号使参考文献按顺序编号格式如 [1]，最后显示为 [Bibliography Number] ，悬挂缩进 Hanging Indent 设为 All paragraphs 。

至此，中文期刊文献输出格式建立完成，最后使用【File】 →【Save As】保存该格式并命名，保存的文件名为 [中文文献输出格式] ，如图所示。
{{< image src="/images/Science/EndNote/EndNoteEC_10.png" caption="Fig. 10. 参考文献布局设置" width="100%" >}}

___

## 4. Word 中的设置
### 步骤11
首先选择输出格式 Style 为 [中文文献输出格式] 。

设置悬挂，点击 word 中的 Bibliography 的下拉菜单，悬挂值一般设置 0.635cm，如图所示。
{{< image src="/images/Science/EndNote/EndNoteEC_11.png" caption="Fig. 11. Word 中的设置" width="80%" >}}


好了，现在你可以在 Word 中实现中英文参考文献混排了！<font color="blue">**祝你写作愉快，毕业快乐~**</font>

