### LaTex环境的安装和配置



#### 下载Tex Live

1. ​		[Tex Live 官网](http://tug.org/texlive/)

2. 可以选择在线安装，但是由于内容比较大，推荐使用`DVD`方式下载，如下所示

   ![image-20200718083151265](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718083151265.png)

   

3. 然后

   ![image-20200718083338862](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718083808737.png)

   

4. 然后

   ![image-20200718083430632](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718083338862.png)

5. 最后从下面的列表中选择一个`.iso`文件进行下载即可

   ![image-20200718083605190](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718083605190.png)



#### 安装Tex Live

1. 下载`.iso`文件完成之后，双击打开该文件，会出现以下内容

   ![image-20200718083808737](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718083430632.png)

   

2. 以管理员方式打开下面这个文件

   ![image-20200718083928454](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718083928454.png)

3. 然后点击`安装`，接下来就是等待安装完成即可



#### 第一个`LaTex`文件

1. 新建一个`.tex`结尾的文件，例如`test.tex`

2. 然后使用任意文本编辑器写入如下内容

   ```latex
   \documentclass{article}
   
   \begin{document}
   
   Hello \LaTeX
   
   \end{document}
   ```

   

3. 然后保存编辑内容，打开命令行窗口，打开`test.tex`文件所在路径，例如

   ![image-20200718163459059](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718163459059.png)

4. 然后就可以使用`latex`命令对`test.tex`文件进行编译

   ```bash
   latex test.tex
   ```

   

5. 编译完成之后会生成如下几个文件

   ![image-20200718163837700](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718163837700.png)

6. 然后我们可以使用`dvipdfmx`命令将`.dvi`文件转换为`.pdf`文件。

   ```bash
   dvipdfmx test.dvi
   ```

   

7. 结果如下

   ![image-20200718164259700](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718164259700.png)

8. 打开`.pdf`文件，内容如下

   ![image-20200718164419292](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718164419292.png)



##### 一步到位的编译命令

1. 上面要生成`.pdf`文件需要依次执行两个命令: `latex`和`dvipdfmx`

2. 实际上我们可以使用`xelatex`命令直接生成`pdf`类型的文件

   ```bash
   xelatex test.tex
   ```

   

3. 结果如下

   ![image-20200718165010364](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718165010364.png)



##### 处理中文信息

1. `LaTeX`默认是不支持中文的

2. 如果文档中把包含中文信息，需要进行以下几个操作：

   - 必须将源文件（也就是`.tex`文件）的编码设置为`UTF-8`
   - 在引言区引入`ctex`宏包

3. 具体例子如下所示

   ```latex
   \documentclass{article}
   
   \usepackage{ctex}
   
   \begin{document}
   
   你好， \LaTeX
   
   \end{document}
   ```

   

4. 其编译结果如下

   ![image-20200718170203590](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718170203590.png)

5. 从上面的例子我们可以知道，**引言区**实际上也就是`\begin`前的区域，引入**宏包**的指令是`usepackage`



#### 安装`TeXstudio`

1. 由于使用文本编辑器编辑然后使用命令行进行编译的方式比较繁琐，效率比较低
2. 因此我们应该使用集成开发环境
3. 比较好的`LaTeX`的集成开发环境可以我们选择的是`TeXstudio`
4. 安装过程如下：
   - 到官网下载相应的软件安装包
   - 傻瓜式`next`安装即可，不需要任何额外的操作
5. 安装完成之后打开



#### `TeXstudio`基本配置

##### 配置中文界面

1. `TeXstudio`的界面默认是英文的，要使用中文要进行如下操作

2.   

   ![image-20200718171354283](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718171354283.png)

   

3.  

   ![image-20200718171501114](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718171638810.png)

   

4.  

   ![image-20200718171638810.png](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718171501114.png)

   

5.  

   ![image-20200718171742724.png](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718171742724.png)

   

##### 配置构建编译器

1. 和上面配置中文界面类似，按照`选项  -> 设置TeXstudio`找到以下界面

   ![image-20200718210250746](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200718210250746.png)

   

2. 按`确定`完成配置



#### END

