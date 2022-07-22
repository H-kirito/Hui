# JAVA语法
[<<Java](/back/java/README)

## 标识符

1. 标识符可以由字母、数字、下划线(_)、美元符($)组成，但不能包含 @、%、空格等其它特殊字符

2. 不能以数字开头。如:123name 就是不合法

3. 标识符严格区分大小写。如: tmooc 和 tMooc 是两个不同的标识符

4. 标识符的命名最好能反映出其作用，做到见名知意。

5. 标识符不能是Java的关键字

### 注意细节：
   
1. 类名命名习惯每个英文单词的首字母都大写
2. 变量（参数）的命名习惯首个单词的首字母小写，其它单词的首字母都大写
3. 常量的命名习惯：所有字母都大写
4. 包名的命名习惯：所有字母都小写

## 关键字

javac -d . demo.java 注: -d 有package时  .当前目录(javac package的地址 demo.java)

生成帮助文档的命令javadoc java文件(xx.java)

~~~java
/**文档注释,在帮助文档文件中显示*/
~~~