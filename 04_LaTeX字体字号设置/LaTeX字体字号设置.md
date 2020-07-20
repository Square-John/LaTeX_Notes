### `LaTeX`字体字号设置



#### 字体属性

在`LaTeX`中，字体有5种属性：

1. 字体编码
   - 正文字体编码：`OT1, T1, EU1`等
   - 数学字体编码：`OML, OMS, OMX`等
2. 字体族
   - 罗马字体：笔画起始处有装饰
   - 无衬线字体：笔画起始处无装饰
   - 打字机字体：每个字符宽度相同，又称**等宽字体**
3. 字体系列
   - 粗细
   - 宽度
4. 字体形状
   - 直立
   - 斜体
   - 伪斜体
   - 小型大写
5. 字体大小



#### 字体族设置

1. 罗马字体设置命令

   ```latex
   \textrm{Roman Family}
   ```

   - 将花括号中的字体设置为罗马字体（**最为常用**）

   或者

   ```latex
   \rmfamily Roman Family
   ```

   - 将后续的字体设置为罗马字体

   又或者

   ```latex
   {\rmfamily Roman Family}
   ```

   - 使用大括号限定罗马字体的作用范围

2. 无衬线字体同理，可以使用`\textsf{Text}`或者是`\sffamily`

3. 打字机字体使用`texttt{Text}`或者`ttfamily`



#### 字体系列设置

1. 中等（正常）字体

   ```latex
   \textmd{Medium Series} % 正常粗细
   \mdseries Medium Series
   ```

   

2. 粗体

   ```latex
   \textbf{Boldface Series} % 粗体
   \bfseries Boldface Series
   ```



#### 字体形状设置

1. 直立

   ```latex
   	% 直立
   	\textup{Upright Shape} \upshape Upright Shape
   ```

   

2. 斜体

   ```latex
   	% 斜体
   	\textit{Italic Shape} \itshape Italic Shape
   ```

   

3. 伪斜体

   ```latex
   	% 伪斜体
   	\textsl{Slanted Shape} \slshape Slanted Shape
   ```

   

4. 小型大写

   ```latex
   	% 小型大写
   	\textsc{Small Caps Shape} \scshape Small Caps Shape
   ```



#### 中文字体设置

1. 中文字体设置首先需要引入`ctex`宏包

2. 中文的字体设置

   ```latex
   {\songti 宋体} \quad {\fangsong 仿宋} \quad {\kaishu 楷书} \quad {\heiti 黑体}
   ```

   

3. 中文也可以使用斜体和粗体的命令

   ```latex
   \textit{斜体} \textbf{粗体}
   ```

   

#### 字体大小设置

1. 字体的大小通过以下这一系列命令实现

   ```latex
   	%字体大小
   	{\tiny Text} \\ % \\用于换行
   	{\scriptsize Text} \\
   	{\footnotesize Text} \\
   	{\small Text} \\
   	{\normalsize Text} \\
   	{\large Text} \\
   	{\Large Text} \\
   	{\LARGE Text} \\
   	{\huge Text} \\
   	{\Huge Text} \\
   ```

   

2. 字体的大小是相对于**默认字体**来说的，默认的字体大小有`10pt, 11pt, 12pt`

3. 默认字体的设置是文档类的一个可选参数，可以通过下面这样的方式进行设置

   ```latex
   \documentclass[10pt]{article}
   ```



#### 中文字号设置

中文字号可以通过以下命令进行设置

```latex
	% 中文字号设置
	\zihao{-0} 小初字号 % 参数-0表示小处字号
	
	\zihao{5} 五号
```



#### 字体命令汇总

1. 字体命令

   ![image-20200720200814348](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200720200837023.png)

2. 字号命令

   ![image-20200720200837023](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200720200814348.png)

#### 本节完整示例

```latex
\documentclass[11pt]{article}

\usepackage{ctex}

\begin{document}
	
	% 字体族设置（罗马字体、无衬线字体、打字机字体）
	\textrm{Roman Family} \textsf{San Serif Family} \texttt{Typewriter Family}
	
	\rmfamily{Roman Family} \sffamily{San Serif Family} \ttfamily{Typewriter Family}
	
	{\rmfamily Roman Family} {\sffamily San Serif Family} {\ttfamily Typewriter Family}
	
	% 字体系列设置
	\textmd{Medium Series} % 正常粗细
	\mdseries Medium Series
	
	\textbf{Boldface Series} % 粗体
	{\bfseries Boldface Series}
	
	% 字体形状
	
	% 直立
	\textup{Upright Shape} \upshape Upright Shape
	
	% 斜体
	\textit{Italic Shape} \itshape Italic Shape
	
	% 伪斜体
	\textsl{Slanted Shape} \slshape Slanted Shape
	
	% 小型大写
	\textsc{Small Caps Shape} \scshape Small Caps Shape
	
	% 中文字体设置
	{\songti 宋体} \quad {\fangsong 仿宋} \quad {\kaishu 楷书} \quad {\heiti 黑体}
	
	\textit{斜体} \textbf{粗体}
	
	%字体大小
	{\tiny Text} \\ % \\用于换行
	{\scriptsize Text} \\
	{\footnotesize Text} \\
	{\small Text} \\
	{\normalsize Text} \\
	{\large Text} \\
	{\Large Text} \\
	{\LARGE Text} \\
	{\huge Text} \\
	{\Huge Text} \\
	
	% 中文字号设置
	\zihao{-0} 小初字号 % 参数-0表示小处字号
	
	\zihao{5} 五号
	
\end{document}
```



#### END

