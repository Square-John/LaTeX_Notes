### LaTeX的篇章结构



#### 篇章结构的实例

下面是一个`LaTeX`篇章结构的例子

```latex
\documentclass{ctexart}

% \usepackage{ctex}

% \ctexset命令用于设置中文提纲的样式，具体可以查看ctex的帮助文档
\ctexset{
	section/format = \Large\bfseries\raggedright
}

\begin{document}

	\tableofcontents % 用于生成文章的目录
	
	%\chapter{第一章} % 这个只有book才有
	
	\section{引言} % 节
	
	\section{实验} 
	
	\subsection{实验过程} % 子小节
	
	\subsubsection{实验步骤} % 子子小节
	
	\subsection{实验数据}
	
	\section{结论}
	
	 % 带*号的小节不会被进行编号，也不会被收入目录中
	\section* {致谢}
	
	\paragraph{孔乙己} %篇
	
	\subparagraph{第一回} % 子篇
	
\end{document}
```

- 其编译结果如下图所示

![image-20200721192626346](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200721192626346.png)



#### 各部分讲解



##### 标题样式设置

以下命令用于设置中文的标题样式，具体可以参考`ctex`的中文手册

```latex
% \ctexset命令用于设置中文提纲的样式，具体可以查看ctex的帮助文档
\ctexset{
	section/format = \Large\bfseries\raggedright
}
```



##### 生成目录

下面的命令用于生成目录

```latex
\tableofcontents % 用于生成文章的目录
```



##### 文章结构主要命令

下面这些是一篇文章（或者是一本书）的主要提纲命令

```latex
	\tableofcontents % 用于生成文章的目录
	
	%\chapter{第一章} % 这个只有book才有
	
	\section{引言} % 节
	
	\section{实验} 
	
	\subsection{实验过程} % 子小节
	
	\subsubsection{实验步骤} % 子子小节
	
	\subsection{实验数据}
	
	\section{结论}
	
	 % 带*号的小节不会被进行编号，也不会被收入目录中
	\section* {致谢}
	
	\paragraph{孔乙己} %篇
	
	\subparagraph{第一回} % 子篇
```

- 其中只有`book`才有`chapter`
- `book`中没有`subsubsection`



##### 其他的一些补充说明

1. `LaTeX`中，使用一个或者多个空行表示**分段符号**
2. 也可以使用`\par`命令进行分段，但是更常用的是空行进行分段
3. 使用`\\`进行换行



#### END

