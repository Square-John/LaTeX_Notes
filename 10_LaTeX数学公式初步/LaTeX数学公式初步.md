### LaTeX数学公式初步



#### 简介

​		LaTeX将排版内容分为文本模式和数学模式。文本模式用于普通文本排版，数学模式用于数学公式排版。



#### 行内公式

​		和普通文本占据同一行，不另行分行的公式叫做行内公式，可以使用三种方式排版得到行内公式



##### 使用$符号

​		使用$符号包围的部分就成为行内公式，例如

```latex
$ a + b = b + a $
```

的排版结果为： $ a + b = b + a $



##### 使用小括号

​		也可以使用小括号包围形成行内公式，例如

```latex
( a + b = b + a )
```

其排版结果为：$ a + b = b + a $

##### 使用math环境

​		例如

```latex
\begin{math}
	a + b = b + a
\end{math}
```

其排版结果为：$ a + b = b + a $



#### 上下标



##### 上标使用`^`表示

```latex
3x^2 + 2 - x = 0
```

的编译结果为$ 3x^2 + 2 - x = 0 $



##### 下标使用`_`表示

```latex
x_1 + x_2 = 5
x_1 - x_2 =3
```

的编译结果为:

$$ x_1 + x_2 = 5 $$
$$ x_1 - x_2 =3 $$ 



##### 注意

1. 对于复合上下标，需要将作为上下标的部分使用`{}`括起来
2. 上下标符号只会把其后紧跟的块作为上下标
3. 如果没有`{}`，LaTeX默认将上下标符号的其后一个字符变为上下标
4. 例如

```latex
x^yz
```

​	的编译结果为：$ x^yz $

​		而

```latex
x^{yz}
```

的编译结果为：$ x^{yz} $



####  希腊字母

1. `LaTeX`中使用反斜杠`\`开头表示一个命令

2. 在`LaTeX`中的希腊字母实际上都是用命令生成的

3. 生成希腊字母的命令就是希腊字母的英文单词

4. 单词的首字母小写则表示相应的小写希腊字母.例如

   ```latex
   \gamma
   ```

   的编译结果为：$ \gamma $

5. 单词的首字母大写则表示相应的大写希腊字母。例如

   ```latex
   \Gamma
   ```

   的编译结果为：$ \Gamma $

6. 更多的希腊字母的表示方法可以百度或者查阅相关的文档



#### 数学函数

1. 和希腊字母一样，`LaTeX`中的数学函数也是通过命令生成的

2. 各个**常用**数学函数的命令也就是其数学函数本身。例如

   ```latex
   \sin x
   \cos y
   ```

   其编译结果为：

   $$ \sin x $$

   $$ cos y $$

3. 这里重点列出一个开方的函数表示，其命令格式为

   ```latex
   \sqrt[根指数]{被开方数}
   ```

   

4. 例如

   ```latex
   \sqrt[3]{8} = 2
   ```

   的编译结果为：$ \sqrt[3]{8} = 2 $



#### 分式



##### 使用`/`分隔表示分式

```latex
3 / 4
```

的编译效果为：$ 3 / 4 $



##### 使用`frac{分子}{分母}命令

```latex
\frac{3}{4}
```

的编译效果为：$ \frac{3}{4} $



#### 行间公式

一个公式独占一行，这样的公式称为行间公式



##### 使用`$$`符号表示

使用`$$`符号包围的部分内容就成为了一个行间公式。例如

```latex
$$ x_1 + x_2 = 5 $$
```

的编译结果为：



独占一行



##### 使用中括号`[]`表示

除了使用`$$`符号，还可以使用`[]`。例如

```latex
[x_1 + x_2 = 5]
```

的编译结果为：

$$ x_1 + x_2 = 5 $$



##### 使用`displaymath`环境表示一个行间公式

例如

```latex
\begin{displaymath}
	x_1 + x_2 = 5
\end{displaymath}
```

其编译结果和上面一样



##### 行间公式自动编号

1. 使用`equation`环境可以实现行间公式的自动编号。例如

   ```latex
   加法交换律见式\ref{commutative1}
   			\begin{equation}
   				a + b = b + a \label{commutative1}
   			\end{equation}
   ```

   其结果如下

   ![image-20200831232526666](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200831232526666.png)

2. 使用`equation`环境不仅能够对公式进行自动编号，还能够结合`ref`和`label`等命令为公式设置标签，从而实现公式的交叉引用



##### `equation*`环境忽略行间公式编号

1. 使用`equation*`环境可以为指定的行间公式设置为没有编号。例如

   ```latex
   乘法交换律见式\ref{commutative2}
   			\begin{equation*}
   				a \times b = b \times a  \label{commutative2}
   			\end{equation*}
   ```

   其编译结果和普通的使用`$$`等括起来的行间公式没有什么本质上的区别

2. 使用该环境，同样可以结合`label`以及`ref`等命令实现公式的交叉引用，引用处使用小节编号代表该公式。例如上面的代码编译结果如下图所示

   ![image-20200831233302502](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200831233302502.png)

3. 实际上我们上面提到的，使用`$$`符号或者中括号`[]`表示行间公式也可以结合`label`和`ref`命令实现行间公式的交叉引用，这其实和`equation*`环境没有什么区别

4. 使用`equation*`环境还需要引入一个宏包`amsmath`



#### 本小节完整实例

```latex
\documentclass{ctexart}

\usepackage{amsmath}

\begin{document}
	
	\section{简介}
	LaTeX将排版内容分为文本模式和数学模式。文本模式用于普通文本排版，数学模式用于数学公式排版。
	
	\section{行内公式}
	
		\subsection{使用\$符号进行行内数学公式的排版}
		交换律是 $ a + b = b + a $
		
		\subsection{使用小括号进行行内公式的排版}
		交换律是 ( a + b = b + a )
		
		\subsection{使用math环境进行行内公式排版}
		交换律是
			\begin{math}
				a + b = b + a
			\end{math}
	\section{上下标}
	
		\subsection{上标使用\^{}}
		例如： $ 3x^2 + 2 - x = 0 $
		
		对于符合上标，使用\{\}将其括起来，否则只有\^{}后面紧接着的那一个字母才会成为上标。例如：$ 3x^{a + b} + y = z $
		
		\subsection{下标使用\_{}}
		例如：$ x_1 + x_2 = 50 $
		
		和上标同理，符合==复合的上标需要使用\{\}括起来才能达到预期效果
		
	\section{希腊字母}
	使用转义字符反斜杠加上希腊字母的英文单词，就可以表示一个希腊字母，格式为：\textbackslash + 希腊字母单词
	
	例如：\textbackslash alpha的结果为 $ \alpha $
	
	如果希腊字母单词首字母大写，就获得大写的希腊字母，例如：
	
	\textbackslash Gamma -> $ \Gamma $
	
	更多的希腊字母表示方式可以百度或者查官方文档
	
	\section{数学函数}
	常用的数学函数只需要使用反斜杠加上其在数学中原本的英文表示就可以了，例如：
	
	\textbackslash sin -> $ \sin $
	
	$ sin x = 1 $
	
	一个比较特殊的函数是开方的函数，表示如下
	
	\textbackslash sqrt[根指数]{被开方数}
	
	例如
	
	$\sqrt[3]{8} = 2 $
	
	\section{分式}
	可以直接使用/表示分式，例如3/4 -> $ 3/4 $ ,其结果就是和输入差不多
	
	还可以使用\textbackslash frac\{分子\}\{分母\}表示一个分式，例如：
	
	\textbackslash frac\{3\}\{4\} -> $ \frac{3}{4} $
	
	\section{行间公式}
	
		\subsection{使用\$\$符号排版行间公式}
		加法交换律：
		$$ a + b = b + a $$
		
		\subsection{使用中括号命令排版行间公式}
		格式为\textbackslash [ 公式 \textbackslash ]
		加法交换律：
		\[ a + b = b + a \]
		
		\subsection{使用displaymath环境排版行间公式}
		加法交换律：
			\begin{displaymath}
				a + b = b + a
			\end{displaymath}
		
		\subsection{使用equation环境进行公式的自动编号}
		此时不仅可以自动编号，还可以使用label和ref命令实现对公式的交叉引用，例如
		
		加法交换律见式\ref{commutative1}
			\begin{equation}
				a + b = b + a \label{commutative1}
			\end{equation}
		
		\subsection{使用equation*环境实现对公式不进行编号}
		此时不会对公式进行编号，但是区别是，普通的行间公式是不能够进行交叉引用的，但是equation*环境中的行间公式虽然没有编号但是可以进行交叉引用，其引用编号为小节号，例如
		
		乘法交换律见式\ref{commutative2}
			\begin{equation*}
				a \times b = b \times a  \label{commutative2}
			\end{equation*}
		
		不过使用该环境需要引入amsmath宏包
		
		\subsection{一些额外说明}
		实际上直接对普通的行间公式也是可以进行交叉引用的，也就是说其实没必要使用equation*环境
	
	
\end{document}
```









 

