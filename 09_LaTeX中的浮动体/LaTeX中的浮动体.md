### LaTeX中的浮动体



#### 浮动体的作用

1. 实现灵活分页（避免无法分割的内容产生的页面空白）
2. 给图表添加标题
3. 实现交叉引用



#### 浮动体设置语法

```latex
\begin{<environment>}[<位置参数>] 
% 其中<environmen>可以是figure,或者table
% figure 就是为图片设置浮动体，table就是为表格设置浮动体

	contents
	
\end{<environment>}
```

- 其中`<environment>`参数可以是`figure`，也可以是`table`
  1. `figure`表示浮动体中的内容是图片
  2. `table`中的表示浮动体中的内容是表格
- `<位置参数>`可以是下面几种：
  1. `h` - `here`：此处，也就是代码所在的上下文的位置
  2. `t` - `top`：页顶，也就是代码所在页面或者之后页面的顶部
  3. `b` - `bottom`：底部，也就是代码所在页面或者之后页面的底部
  4. `p` - `page`：独立一页，这个页面也称为浮动页面



#### 浮动体中常用的一些命令

1. 设置浮动体的对齐方式命令，例如`\centering`等
2. `caption{<Title>}`命令用于设置浮动体的标题
3. `label{<tag>}`用于设置浮动体的标签，标签用于交叉引用
4. `ref{<tag>}`用于引用一个`tag`所指定的浮动体



#### 示例

```latex
\documentclass{ctexart}

\usepackage{graphicx}

\graphicspath{{figures/}}

\begin{document}
	
	如下图\ref{save}是一个表示保存含义的图标 \\
	\begin{figure}[h] % h表示图片排在代码所在行
		
		\centering % 表示居中排版
		
		\includegraphics[scale=2]{save} % 引入图片
		
		\caption{保存图标} % 设置标题
		
		\label{save} % 设置标签名
		
	\end{figure}

下面表\ref{table1}是一个成绩表

	\begin{table}[h]
		
		\centering
		
		\caption{成绩表}
		
		\label{table1}
		
		\begin{tabular}{|c| c| c|}
			
			\hline			
			姓名 & 语文 & 英语 \\			
			\hline			
			张三 & 90	 &  80 \\			
			\hline
			
		\end{tabular}
		
	\end{table}
	
\end{document}
```

- 编译结果如下图

![image-20200725164427699](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200725164427699.png)





#### 更复杂的浮动体控制

1. 标题控制可以参考：`caption, bicaption`等宏包
2. 并排与子图表参考：`subcaption,  subfig, floatrow`等宏包
3. 绕排：`picinpar, wrapfig`等宏包