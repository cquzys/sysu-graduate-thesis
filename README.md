# SysuGraduateThesis

中山大学计算机学院研究生毕业论文 LaTeX 模板,包括硕士和博士论文等， 基于[ThuThesis](https://github.com/tuna/thuthesis)项目开发

关于开发模板的相关说明请参考 [https://github.com/tuna/thuthesis](https://github.com/tuna/thuthesis)


## 特别说明
- 以下的说明只作为参考，详细如何用Latex编写论文，需要学习Latex的基本语法，我们在这里只是抛砖引玉，给
大家提供一个使用Latex撰写中大硕博论文的简介。


## 背景说明
- TeX 的源代码是后缀为 .tex 的纯文本文件。使用任意纯文本编辑器，都可以修改 .tex 文件：包括 Windows 自带的记事本程序，也包括专为 TeX 设计的编辑器
（TeXworks, TeXmaker, TeXstudio, WinEdt 等），还包括一些通用的文本编辑器（Sublime Text, Atom, Visual Studio Code 等）。
你可以在这些能够编辑纯文本文件的编辑器中任选其一作为你的 TeX 编辑器，也可以使用 TeX 发行自带的编辑器。最流行的两个 TeX 发行（TeX Live 和 MiKTeX）都带有 TeXworks 编辑器。

- 所谓 TeX 发行，也叫 TeX 发行版、TeX 系统或者 TeX 套装，指的是包括 TeX 系统的各种可执行程序，以及他们执行时需要的一些辅助程序和宏包文档的集合。



## 配置环境  
- Windows 
	- 需要提前先安装TexLive 2020  (具体参考当前最新的版本)
- 字体 (Linux用户需要注意):   
    - times.ttf  
    - simhei.ttf  


## 平台使用说明 
- 首先从 GitHub clone 项目源码或者下载源码 zip 包，然后选择平台
- 在OverLeaf平台上使用方法
	- 在overleaf点击创建newPorject, 上传压缩版的本项目（zip格式）
	- 在overleaf界面，点击左上角的main按钮，选择settings中的compiler， 选择XeLaTex编译器
	- 编译`main.tex`
	
- 在Windows上使用方法
	- 下载本项目到本地的windows环境，前提要配置好tex环境，即需要先安装最新的Texlive（latex的运行环境），具体可参考网上windows latex环境使用依赖需求。
	- 安装好latex的使用依赖环境后，使用步骤如下：
		- 找到应用程序并且打开 TeXworks editor，或者是自己安装一个latex文档编辑器（背景说明里有描述）
		- 在编辑器中打开下载项目中的main.tex文件，然后选择XeLaTex编译器，然后直接编译`main.tex`文件即可。
		- 点击view按钮，可以看到对应的pdf文件。
	- 参考文献的编译方式：和main.tex稍有区别的是：maix.tex直接编译，即可生成对应的pdf。但是参考文献的编译方式如下：
		- 用XeLaTex编译你的 .tex 文件 , 这是生成一个 .aux 的文件, 这告诉 BibLaTeX 将使用那些应用
		- 用BibLaTeX 编译 .bib 文件
		- 再次用XeLaTex 编译你的 .tex 文件，这个时候在文档中已经包含了参考文献，但此时引用的编号可能不正确
		- 最后用 XeLaTex 编译你的 .tex 文件，如果一切顺利的话, 这是所有东西都已正常了
	

## Latex排版工具
- TeXworks 为我们预设了若干排版工具（pdfTeX, pdfLaTeX, XeTeX, XeLaTeX 等），本项目主要用到其中的 XeLaTeX。关于这些排版工具的细节，讲解起来会有些复杂。
因此此处不细讲，可以百度。当你对 TeX 系统相当熟悉之后，也可以不使用 TeXworks 预设的工具，自己配置排版工具。

- TeXworks 默认的排版工具是 pdfLaTeX。如果你希望更改这个默认值，可以在编辑 - 首选项 - 排版 - 处理工具 - 默认 中修改。


## 使用说明 
- `main.tex`: 用于编写论文主体部分
	- 关于硕博论文选择
		- `main.tex`中，在代码：`\documentclass[degree=doctor]{sysuthesis}`这一行，如果是硕士论文，用master, 如果是博士论文，用doctor
- 目录结构说明
	- 主要修改的是main.tex文件，main.tex文件里有每一行代码的详细描述。
	- main中的的主体部分都放在data目录下。通过\input的方式引入到main.tex中，最后并统一通过maix.tex生成pdf显示（完成撰写后，编译main.tex即可）。
	- main.tex文件的主体包括：abstract， denotation， chapter， ref, appendix等。各部分的格式在对应的文件中都有详细描述，如何将各部分引入到main.tex中，在mian.tex中有详细的注解。


## 撰写论文各章节说明 
- `sysusetup.tex`: 填写论文标题, 学位类别, 学院, 专业等基本信息; 加载宏包; 定义参考文献格式  
- `data/abstract.tex`: 填写摘要  
- `data/denotation.tex`: 缩略语和符号, 请**按照字母顺序(A-Z)罗列**  
- `data/chap*.tex`: 章节内容, 如果需要增添需要在`main.tex`里修改相关记录  
- `data/acknowledgements.tex`: 致谢  
- `data/resume.tex`: 简历及论文发表情况 
- 其他部分可参考data目录下的每一个文件，都有详细说明，且在main.tex中都可以看到如何引入他们，并进行编译显示。 


## 样式控制
- `.bbx结尾的文件`: 用于列表样式控制
- `.cbx结尾的文件`: 引用样式控制
- `.bst结尾的文件`: 排版样式控制 
- `.cls结尾的文件` :是类文件，用于控制main的主题风格
- `ins` 文件通常用来控制TeX 从 `.dtx` 文件里释放宏包文件



## 参考文献格式说明 
- 期刊论文
	- 规定：［序号］.作者.文章题目.刊名，出版年份，卷号（期号）：页码
	- 示例：
		- 〔1〕梁柱.论高等学校在未来终生教育体制中的地位和作用.北京大学学报（哲学社会科学版），1997,3： 79—84
		- 〔2〕PELAGTTI P,BACCHI A,CARCELL M,et al. Palladium complexes containing a P, N chelating ligand Part Ⅲ.J Organomet Chem,1999,583:94—105
- 会议论文
	- 规定：［序号］作者.篇名.出版地：出版者，出版年份：起始页码. 
	- 示例：
		- 〔3〕伍蠡甫.西方文论选. 上海：上海译文出版社，1979：12-17.
		- 〔4〕Spivak,G. Victory in Limbo. Urbana: University of Illinois Press, 1988, pp.271-313.
- 著作
	- 规定：［序号］作者.书名.出版地：出版社，出版年份：起止页码.
	- 示例：
		- 〔5〕 张志建.严复思想研究. 桂林：广西师范大学出版社，1989.
		- 〔6〕Gill, R. Mastering English Literature. London: Macmillan, 1985: 42-45.


