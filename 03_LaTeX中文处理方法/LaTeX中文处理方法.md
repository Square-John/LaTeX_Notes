### LaTeX中文处理办法



#### 在导言区引入`ctex`宏包

##### 基本用法

1. 首先`选项 -> 设置TeXstudio -> 构建`，设置默认编译器为`XeLaTeX`

   ![image-20200719190655164](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719190655164.png)

   

2. 设置编辑器的默认编码格式为`UTF-8`

   ![image-20200719190914862](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719190914862.png)

   

3. 在导言区使用`\usepackage{ctex}`命令引入一个用于处理中文的宏包`ctex`。如下示例

   ```latex
   % 导言区
   \documentclass{article}
   
   \usepackage{ctex} % 用于处理中文的宏包
   
   \title{勾股定理} % 标题
   \author{张三} % 作者
   \date{\today} % 日期
   
   \begin{document}
   	
   	\maketitle % 显示标题信息
   	
   \end{document}
   ```

   - 其编译结果如图所示

   ![image-20200719193001468](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719193001468.png)

##### 一些知识的先修

1. 我们还可以设置标题等所使用的字体，详细的字体设置后面有讲述，这里给出一个简单的示例

   ```latex
   \title{\heiti 勾股定理} % 标题 我们还可以设置字体为黑体
   \author{\kaishu 张三} % 作者
   ```

2.  我们还可以在导言区自定义一个新的命令，如何定义一个新的命令后面也会有教程，这里给出一个简单示例

   ```latex
   \newcommand{\degree}{^\circ} % 定义一个新的命令\degree表示°
   ```

3. 定义一个带编号的行间公式方法如下

   ```latex
   \begin{equation} % 使用equation参数，表示这是一个带编号的行间公式	
   	AB^2 = 	BC^2 + AC^2.	
   	\end{equation}
   ```

   - 其效果如图

   ![image-20200719193946609](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719193946609.png)

   

##### 完整示例

```latex
% 导言区
\documentclass{article}

\usepackage{ctex} % 用于处理中文的宏包

\newcommand{\degree}{^\circ} % 定义一个新的命令\degree表示°

\title{\heiti 勾股定理} % 标题 我们还可以设置字体为黑体
\author{\kaishu 张三} % 作者
\date{\today} % 日期

\begin{document}
	
	\maketitle % 显示标题信息
	
	勾股定理：直角三角形的斜边长度的平方等于两腰的各自长度的平方之和。
	
	设三角形$ ABC $，其中$ \angle C = 90\degree $，则有
	\begin{equation}	
	AB^2 = 	BC^2 + AC^2.	
	\end{equation}
	
\end{document}
```

- 其编译结果如下

![image-20200719193446202](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719194426217.png)



#### 查看`LaTeX`的帮助文档

1. 我们可以使用`texdoc`命令查看相应的宏包等的帮助文档。例如我们想要查看`ctex`宏包的帮助文档，我们就可以使用如下命令

   ```bash
   texdoc ctex
   ```

   

2. 在`cmd`窗口输入上面的命令并回车之后就会出现下图这样的`ctex`帮助文档

   ![image-20200719194426217](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719194728450.png)

   

3. `LaTeX`有一份中文版的`LaTeX`教程文档，我们可以通过以下命令来查看

   ```bash
   texdoc lshort-zh
   ```

4. 文档内容如下

   ![image-20200719194728450](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719193446202.png)



#### 使用`ctex`文档类

1. `ctex`宏集手册中有如下的描述

   ![image-20200719194940617](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719194940617.png)

   

2. 也就是说如果我们需要处理中文我们除了上面那种在导言区引入`ctex`宏包之外还可以使用`ctex`提供的四个中文文档类

3. 使用方法就是将`\documentclass{arg}`中的参数设置为`ctexart, ctexrep, ctexbook, ctexbeamer`

4. 这样就不用在导言区引入`ctex`宏包就可以使得文档支持中文了

5. 具体示例如下

   ```latex
   % 导言区
   \documentclass{ctexart} % 只需要将参数更换为ctexart
   
   % \usepackage{ctex} % 用于处理中文的宏包 % 这个引入包命令就不需要了
   
   \newcommand{\degree}{^\circ} % 定义一个新的命令\degree表示°
   
   \title{\heiti 勾股定理} % 标题 我们还可以设置字体为黑体
   \author{\kaishu 张三} % 作者
   \date{\today} % 日期
   
   \begin{document}
   	
   	\maketitle % 显示标题信息
   	
   	勾股定理：直角三角形的斜边长度的平方等于两腰的各自长度的平方之和。
   	
   	设三角形$ ABC $，其中$ \angle C = 90\degree $，则有
   	\begin{equation}	
   	AB^2 = 	BC^2 + AC^2.	
   	\end{equation}
   	
   \end{document}
   ```

   - 其结果如下

   ![image-20200719195506498](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200719195506498.png)

   



#### END