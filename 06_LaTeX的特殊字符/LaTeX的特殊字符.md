### LaTeX的特殊字符



#### 空白符号



##### 注意事项

1. 空行分段，多个空行等同于一个
2. 自动缩进，绝对不能用空格代替
3. **英文中多个空格会被当作一个来处理，也就是直接书写多个空格无效**
4. 中文的空格将会被忽略
5. 汉字与其他字符的间距由`LaTeX`进行自动处理
6. 禁止使用中文全角空格



##### 空格命令

1. 产生一个`1em`大小的空格（也就是当前字体中一个常规字体大小的空格）

   ```latex
   \quad
   ```

   

2. 产生一个`2em`的空格

   ```latex
   \qquad
   ```

   

3. 产生一个`1/6em`大小的空格

   ```latex
   \thinspace
   ```

   

4. 产生一个`0.5em`大小的空格

   ```latex
   \enspace
   ```

   

5. 使用转义符号产生一个空格

   ```latex
   \[空格符]
   ```

   

6. 产生一个硬空格

   ```latex
   ~
   ```

   

7. 产生指定大小的空格(`1pc = 12pt = 4.218mm`)

   ```latex
   \kern 1pc 
   \hskip 1pc
   \hspace{1pc}
   ```

   - 这些命令的参数还可以使用**负值**，负值就是使两个字符重叠

8. 根据占位字符的宽度产生空白

   ```latex
   \hphantom{xyz}
   ```

   

9. 弹性长度

   ```latex
   \hfill
   ```

   

#### 特殊字符

1. 在`LaTeX`中，`#, $, %, ~, _, ^, &, \`具有特殊含义，因此如果需要在文本中显示这些符号需要进行转义

2. 具体如下

   ```latex
   	\# % #
   	
   	\$ % $
   	
   	\% % %
   	
   	\^{} % ^
   	
   	\_{} % _
   	
   	\~{} % ~
   	
   	\textbackslash % \
   	
   	\& % &
   ```

   - 结果如图

   ![image-20200721202218686](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200721202218686.png)



#### 排版符号

```latex
	\S
	
	\P
	
	\dag
	
	\ddag
	
	\copyright
	
	\pounds
```

- 结果如下图

![image-20200721202531637](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200721202531637.png)





#### 引号

1. `LaTeX`中，引号有单引号和双引号，并且有左右之分

2. 下面是各个引号所使用的符号

   ```latex
   	` % 左单引号
   	
   	' % 右单引号
   	
   	`` % 左双引号
   	
   	'' % 右双引号
   ```

   - 结果如下

   ![image-20200721202911514](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200721202911514.png)

   

#### 连字符

```latex
	- % 短连字符
	
	-- % 中连字符
	
	--- % 长连字符
```

- 结果如下

![image-20200721203124537](https://cdn.jsdelivr.net/gh/Square-John/Image/img/image-20200721203124537.png)



#### END

