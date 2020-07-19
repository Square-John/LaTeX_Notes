### LaTeX源文件的基本结构



#### 基本结构

```latex
% 导言区
\document(article) %book, report, letter

% 正文区（文稿区）
\begin(document) %一个LaTeX源文件有且仅有一个document环境

	内容

\end(document)
```



#### 导言区

1. LaTeX的导言区==主要用于进行全局设置==

2. 比如我们可以在导言区使用以下语句为文章设置标题、作者和日期

   ```latex
   % 使用\title命令设置文档的标题
   \title{Hello World}
   
   % 使用\author设置文档的作者
   \author{Square John}
   
   % 使用\date设置文档的日期，其中\today表示今天
   \date{\today}
   ```

   

3. 可以在文章的正文区使用`\maketitle`命令显示导言区设置的标题信息



#### 正文区

1. 正文区由以下命令包含

   ```latex
   \begin{document}
   
   	内容
   
   \end{document}
   ```

   

2. 其中正文的内容可以是==命令==，也可以是==普通文本==或者是==数学公式==

   ```latex
   \begin{document}
   
   	\maketitle % 这是一个命令
   	
   	This is a general text %普通文本在文本模式进行书写，也就是默认的模式
   	
   	$ f(x) = x^2 - 1 $ % 使用$符号包含的部分称为数学模式，其中单$包围的是行内公式
   	
   	$$ f(x) = x^2 - 1 $$ % 双$ 符号包含的是行间公式，独立占一行
   
   \end{document}
   ```

   - 如上所示，正文区可以包含命令
   - 默认的输入模式是**文本模式**，输入的内容作为普通文本处理
   - 使用`$`符号包围的部分是**数学模式**，输入的内容会被当做数学公式进行处理
   - `$`包含的部分是==行内公式==，公式和其他文本同在一行，不进行换行
   - `$$`包含的部分为==行间公式==，公式独占一行

3. 在正文区，我们可以使用**一个或者多个空白行**作为分段符号。`LaTeX`将多个空白行视为一个空白行，并将其视为一个**分段符号**

4. `LaTeX`的**行注释符号**为**`%`**。`%`号之后的内容为注释内容，不作为文档的实际内容进行编译。



#### 完整示例

```latex
% 导言区

\documentclass{article}

\title{First LaTeX Document} % 设置文档的标题

\author{Square John} % 设置文档的作者

\date{\today} % 设置文档的日期

% 正文区
\begin{document}
	
	\maketitle % 用于显示导言区设置的标题、作者和日期信息
	
	Hello!
	
	% 使用空白行表示换行，LaTeX将多个空白行当作一个空白行处理，也就是将多个空白行视为一个分段符号
	
	Let $ f(x) $ be defined by the formula % 在单个$符号包含范围内称为数学模式，用于书写行内数学公式
	$$ f(x) = 3x^2 + x-1 $$  % 在双$$范围内也是数学模式，用于书写行间数学公式
		which is a polynomial of degree 2. % 这种在$符号包含范围外的称为文本模式
	
\end{document}
```



- 编译结果如下图

![image-20200719191603704](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719191603704.png)



#### END

