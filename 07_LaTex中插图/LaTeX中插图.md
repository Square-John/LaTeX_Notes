### LaTeX中插图



#### 插图步骤

1. 导入包：`\usepackage{graphicx`
2. 插图语法：`\includegraphics[<选项>]{<文件名>}`
   - 其中选项可以来指定图像的高度，宽度，旋转角度等，也可以省略
   - 文件名可以带后缀，也可以不带后缀
3. 指定文件路径：`\graphicspath{{path1/}, {path2/}, ...}`



#### 示例

```latex
\documentclass{article}

% 在LaTeX中插入图像，需要以下几步：
% 1. 导入包：\usepackage{graphicx}
% 2. 插图语法：\includegraphics[<选项>]{<文件名>}
%	其中选项可以来指定图像的高度，宽度，旋转角度等，也可以省略
%	文件名可以带后缀，也可以不带后缀
% 3. 指定文件路径：\graphicspath{{path1/}, {path2/}, ...}

\usepackage{graphicx}

\graphicspath{{figures/}}

\begin{document}
	
	\includegraphics{figure1} %不带可选项参数，图像为原图大小
	
	\includegraphics[scale=1.5]{figure1} % scale=1.5表示放大1.5倍
	
	\includegraphics[height=0.1\textheight]{figure1} % height为0.1的版高
	
	\includegraphics[width=0.1\linewidth]{figure1} % width为0.1的版宽
	
	\includegraphics[height=2cm, width=2cm]{figure1} %还可以同时指定多个参数，用逗号分隔
	
\end{document}
```

- 结果如图

![image-20200721205823000](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200721205823000.png)



#### 插图文档

使用以下命令可以了解更多的插图有关的设置

```latex
texdoc graphicx
```



#### END

