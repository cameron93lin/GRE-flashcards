CodeName GRE FlashCard
====
受CodeName桌游的启发，发现可以通过桌游的形式背诵单词，且效果极佳。因此利用Eroica-cpp的GRE-flashcard(https://github.com/Eroica-cpp/GRE-flashcards)的代码为基础进行修改，实现了相应的卡片制作

说明
----
* **utils文件夹** 里面是简单的python脚本，把markdown文件转换成LaTeX代码，同时排好序保证正反面相对应。运行脚本时会提示输入行列数
```Bash
# 转到utils目录，执行:
python md2latex.py
```

* **src 文件夹** 里面是tex文件。LaTeX方面主要用了beamer库，也就是说一个单词的一面对应一个slide。
```Bash
# tex文件用xelatex编译
xelatex flashcards.tex
```

* **data 文件夹** 里面是原始的markdown文件，是我从[liurui39660](https://github.com/liurui39660)的[3000](https://github.com/liurui39660/3000)repo中的xls文件通过python转换出来的，总共3000个左右《再要你命3000》的单词。可以将md文件替换以实现自定义单词卡

制作方法
----
* **步骤一：Clone这个repo或者直接点击[这里](https://github.com/cameron93lin/GRE-flashcards/archive/master.zip)下载并解压** [GRE-flashcards-all.pdf](https://github.com/cameron93lin/GRE-flashcards/raw/master/download/flashcards.pdf)，

* **步骤二: 执行**

```Bash
python3 utils/md2latex.py
```

在src/content/words文件夹中生成tex文件

* **步骤三: 生成pdf文件**
	* Mac OS:下载安装[TexShop](https://pages.uoregon.edu/koch/texshop/texshop-64/texshop.zip),使用该程序打开src/flashcards.tex, 使用xelatex编译,生成PDF文件并保存
	* Linux: ```
	xelatex flashcards.tex
	```

* **步骤四： 打印这个pdf文件。**
使用Acrobat Pro CC打开PDF, 选择打印, 根据你设置的行列,选择布局,将行列数输入至相应的位置,点击打印即可。正反面已经设置好了,例如你选择2 x 2 即：
```
1 | 2
-----
3 | 4
-----
5 | 6
```
上面是一张A4的一面的结构，1-6表示pdf文件里面的页码。顺序都是程序调过的，按照上面的设置，正反面正好可以对上。

* **步骤五：裁剪。** 打印店一般都有专门裁纸的机器，裁开即可。

如何拓展？
----
* *修改或增加单词：* 修改`data`文件夹内相应的`md`文件。
* *修改字号和字体：* 修改`src`文件夹下的`tex`文件。

感谢
----
[Eroica-cpp](https://github.com/Eroica-cpp)

许可证
---
[The MIT License (MIT)](https://mit-license.org/)
