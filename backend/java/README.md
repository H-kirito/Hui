# 1. Java概述

## 1.1 java语言发展过程

詹姆斯•高斯林（James Gosling）1977年获得了加拿大卡尔加里大学计算机科学学士学位，1983年 获得了美国卡内基梅隆大学计算机科学博士学位，毕业后到IBM工作，设计IBM第一代工作站NeWS系统，但不受重视。后来转至Sun公司，1990年，与Patrick，Naughton和Mike Sheridan等人合作“绿色计划”，后来发展一套语言叫做“Oak”，后改名为Java。

Java之父

![logo](javafather.png)

## 1.2 Java技术体系

>1. Java Card
>2. Java ME
>3. JavaSE
>4. JavaEE

## 1.3 Java语言特点

>1. 简单性
>2. 安全性
>3. 面向对象
>4. 高性能
>5. 跨平台

## 1.4 跨平台

平台指的计算机的安装的操作系统

## 1.5 Java的JVM

JVM是Java Virtual Machine（Java虚拟机）的缩写。

## 1.6 Java语言的发展前景

Java这门语言之所以有优势，也在于它的应用范围十分广泛，房产、医疗、银行、汽车、金融、保险、物流这些行业的公司有软件开发和设计的需求存在，Java就可以展其所长。Java除了一般的编程，还可以开发游戏、进行桌面设计、JavaWeb网站项目开发，可以说Java的就业前景十分乐观，也比较直观。只要有着一定基础的Java程序员不断地跟紧行业里的前沿技术，努力丰富、提高自身的技术，就业是不成问题的。

# 2. JAVA语法

## 2.1 标识符

>1. 标识符可以由字母、数字、下划线(_)、美元符($)组成，但不能包含 @、%、空格等其它特殊字符
>2. 不能以数字开头。如:123name 就是不合法
>3. 标识符严格区分大小写。如: tmooc 和 tMooc 是两个不同的标识符
>4. 标识符的命名最好能反映出其作用，做到见名知意。
>5. 标识符不能是Java的关键字

### 2.1.1 注意细节：
   
>1. 类名命名习惯每个英文单词的首字母都大写
>2. 变量（参数）的命名习惯首个单词的首字母小写，其它单词的首字母都大写
>3. 常量的命名习惯：所有字母都大写
>4. 包名的命名习惯：所有字母都小写

## 2.2 关键字

javac -d . demo.java 注: -d 有package时  .当前目录(javac package的地址 demo.java)

生成帮助文档的命令javadoc java文件(xx.java)

~~~java
/**文档注释,在帮助文档文件中显示*/
~~~

# 3. Java语句

## 3.1 IDEA

IDE:集成开发环境（IDE，Integrated Development Environment ）是用于提供程序开发环境的应用程序 

> psvm:public static void main(String[] args){}

> sout:System.out.println();

> (Scanner方法名).nextLine().var

project和module:project包含module

## 3.2 流程语句

顺序，分支（比较，逻辑表达式），循环

nextLine():一行字符串

### 3.3.1 if、if else

### 3.3.2 Scanner

### 3.3.3 switch(常量表达式)

常量表达式数据类型:

>- 整数类型byte,short,int
>- 字符类型:char
>- 枚举类型:enum JDK1.5之后支持
>- 字符串类型:String JDK7之后支持


    switch(num){
        case 1:
        case 2:
        case 3:
            System.out.println("123");
        case 4:
            System.out.println("4");
            break;
        default:
            System.out.println("de");
            break;
    }

>- num=1或2或3,则都执行System.out.println("123");

# 4. Java循环

循环结构语句

## 4.1 for

    for(初始化语句;条件判断语句;条件控制语句){
        循环体语句
    }

>- 初始化语句
>- 条件判断语句
>- 条件控制语句
>- 循环体语句

## 4.2 while

    初始化语句;
    while(条件判断语句){
    	循环体语句;
        条件控制语句;
    }

## 4.3 do while

    初始化语句;
    do{
    	循环体语句;
        条件控制语句;
    }while(条件判断语句);

>- do while语句至少运行一次循环体

## 4.4 break

>- 循环语句中跳出循环

## 4.5 continue

>- 结束当前循环，进行下一次循环
>- 只能用于循环

    for(int i=1;i<=5;i++){
        if(i==3)
            continue;
    	System.out.println(i);
    }

## 4.6 Random

### 4.6.1 获取随机数

>- 导入包
>- 创建随机数对象
>- 通过对象调用

    import java.util.Random;

    Random random=new Random();

    int randNumber=random.nextInt(bound:10);//[0,10)

### 4.6.2 Guess数字

    public class Guess {
        public static void main(String[] args) {
            Random random = new Random();
            int num = random.nextInt(100)+1;
            Scanner scanner = new Scanner(System.in);
            int count=0;
            while(true){
                System.out.println("猜数字，提示：在1~100之间哦");
                int Guess = scanner.nextInt();
                if(Guess>num){
                    count++;
                    System.out.println("猜大了");
                } else if(Guess<num){
                    count++;
                    System.out.println("猜小了");
                } else{
                    count++;
                    System.out.println("猜对了！");
                    System.out.println("共猜了"+count+"次");
                    break;
                }
    
            }
        }
    }

## 4.7 嵌套循环

### 4.7.1 九九乘法表

    public class Demo {
        public static void main(String[] args) {
            System.out.println("九九乘法表：");
            for(int i=1;i<=9;i++) {
                for (int j = 1; i - j >= 0; j++) {
                    //int j=1；j<=9;j++
                    System.out.print(j + "*" + i + "=" + i * j + "\t");
                }
                System.out.println();
            }
        }
    }

### 4.7.2 等腰三角形

    public class Mode2 {
        public static void main(String[] args) {
            int row=5;
            int count=1;
            for (int i = 1; i <=row; i++) {
                for(int j=row;j>i;j--){
                    System.out.print(" ");
                }
                for (int j = 1; j <=i*2-1 ; j++) {
                    System.out.print("*");
                }
                System.out.println();
            }
        }
    }

# 5. Java方法

## 5.1 方法(method,function)

- 解决代码冗余问题，可重复使用

- 方法的使用
  - 定义方法
  - 调用方法
      public static void 方法名(){ 
          方法体;
      }

## 5.2 方法的参数

- 形式参数
      public static void 方法名(类型 形参名){ 
          方法体;
      }
- 实际参数
      public static void main(String[] args) {
      	方法名(实参);//数据
      }



## 5.3 return

- 返回值是通过关键字return实现的.
- 返回值类型一定和return后面的数据类型,一定保持一致.

1、返回方法指定类型的值（这个值总是确定的），也可以是对象

2、结束方法，终止“return;”后面代码的执行

## 5.4 方法的重载

- 方法名相同，方法参数不同
  方法名相同，方法参数类型不同	

## 5.5 可变参数

    public static 数据类型 add(int... params){
        //params(可变参数名称)
        //可变参数必须放参数列表最后
        方法体;
        return 数据;
    }



### 5.5.1 递归求阶乘

    public static int fact(int n){
        if(n == 1) 
            return 1;
        return fact(n-1) * n;
    } 

## 5.6 数组

### 5.6.1 数组特点

>- 数组保存的数据类型相同
>- 数组可保存多个数据
>- 数组长度是固定的

### 5.6.2数组创建

>- 动态数组
>- 静态数组

## 5.7 方法细节

### 5.7.1 成员变量

>- 定义在方法外的变量
>- 可不赋值，一般有默认值

### 5.7.2 局部变量

>- 定义在方法内的变量

引用类型变量没赋值，默认为null

方法的参数为基本类型，会在栈内存中执行

方法的参数为引用类型，数据会在堆空间保存

# 6. Java数组

## 6.1 数组创建

>- 动态数组
>  - 数据类型[] 数组名称=new 数据类型[长度];
>- 静态数组
>  - 数据类型[] 数组名称={x1,x2,x3};

## 6.2 索引

## 6.3 数组取值，赋值

## 6.4 数组遍历

- 案例：求int类型数组的最大值
      public static void main(String[] args) {
              int[] maxNum={2,1,6,9,1};
              for (int i = 0; i < maxNum.length-1; i++) {
                  if (maxNum[i] > maxNum[i+1]) {
                      maxNum[i+1]=maxNum[i];
                  }
              }
              System.out.println(maxNum[maxNum.length-1]);
      
          }

## 6.5 数组数据顺序调换

### 6.5.1 方法一
      public static void main(String[] args) {
                  int[] oldNum = {2, 1, 6, 9, 1};
                  int[] newNum =new int[5];
                  int j=0;
              for (int i = oldNum.length-1; i >=0; i--) 		{
                  int a=oldNum[i];
                  newNum[j]=a;
                  j++;
              }
              for (int i : newNum) {
                  System.out.print(i+",");
              }
      }

### 6.5.2 方法二
      public static void main(String[] args){
          int[] arr={1,3,4,1,7};
          for(int i=0;i<(arr.length/2);i++){
              int temp=arr[i];
              arr[i]=arr[arr.length-1-i];
              arr[arr.length-1-i]=temp;
          }
          for (int i : arr) {
              System.out.print(i+",");
          }
      }

## 6.6 Random

>- 随机获取数组值


## 6.7 JVM内存分配情况(浅谈)

>- 栈内存 先进先出
>- 堆内存
>   保存引用类型对象
>   当对象不被引用(指对象不再使用)，对象最终被java的GC回收


## 6.8 数组的扩容

扩容：改变数组的长度

分析：数组的长度是固定的，该如何扩容

思路：

>- 1.新建一个数组，指定扩容后的长度
>- 2.将原有数组的数据设置到新的数组里面
>- 3.将新建的数组再赋值给原有数组，完成原有数组的扩容

# 7. JavaDeBug

## 7.1 DeBug

Bug：程序中的故障（程序中的异常或错误）

DeBug：通过调试程序，排除程序中的故障

## 7.2 BreakPoints断点

DeBug对程序进行调试，通过设置断点让程序停下来

## 7.3 概述

可以在一次调试中设置断点，下一次只需让程序自动运行到设置断点位置，便可在上次设置断点的位置中断下来，极大的方便了操作，同时节省了时间。 

# 8. JavaArraysTools

## 8.1 "遍历"数组的方法

    Arrays类定义方法
    toString(类型[] 数组名称);

## 8.2 Arrays排序(底层使用快速排序算法)

    Arrays类定义方法
    sort(类型[] 数组名称);
    sort(T[] a,Comparator<? super T> c);
    //根据对象里的数值属性进行排序，在排序时指定Comparator

## 8.3 比较

    Arrays
    static boolean equals(类型[] 数组名称,类型[] 数组名称)

## 8.4 将数组转成集合

    static <T> List<T> asList(T... a);
    //a为可变参数，其实就是数组，将数组转换成集合

# 9. Java二维数组

## 9.1 二维数组

Java并不直接支持二维数组
但是允许定义数组元素是一维数组的一维数组，以达到同样的效果

> type arrayName[][];   // 数据类型 数组名[][];
> type[][] arrayName;   // 数据类型[][] 数组名;

> type[][] arrayName = new type[][]{值1,值2,值3,…,值n};   // 在定义时初始化
> type[][] arrayName = new type[size1][size2];   // 给定空间，在赋值
> type[][] arrayName = new type[size][];   // 数组第二维长度为空，可变化

## 9.2 排序算法（大到小，小到大）

### 9.2.1 冒泡排序

    public class Demo1 {
            //冒泡排序
            //从小到大排序
            public static void main(String[] args) {
                int[] num ={2,4,7,5,1};
                for (int i = 0; i <num.length-1 ; i++) {
                    for (int j = 0; j <num.length-i-1 ; j++) {
                        if(num[j]>num[j+1]){
                            int temp=num[j];
                            num[j]=num[j+1];
                            num[j+1]=temp;
                        }
                    }
                }
                System.out.println(Arrays.toString(num));
            }
    }


### 9.2.2 选择排序

    public class Demo2 {
            //选择排序
            //从小到大排序
            public static void main(String[] args) {
                int[] num ={2,4,7,5,1};
                for (int i = 0; i <num.length-1 ; i++) {
                    for (int j = i; j <num.length ; j++) {
                        if(num[i]>num[j]){
                            int temp=num[j];
                            num[j]=num[i];
                            num[i]=temp;
                        }
                    }
                }
                System.out.println(Arrays.toString(num));
            }
    }


### 9.2.3 插入排序

    public class Demo {
        //插入排序
        //从小到大排序
        public static void main(String[] args) {
            int[] num ={2,4,7,5,1};
            for (int i = 0; i <num.length ; i++) {
                for (int j = i; j >0 ; j--) {
                    if(num[j]<num[j-1]){
                        int temp=num[j];
                        num[j]=num[j-1];
                        num[j-1]=temp;
                    }
                }
            }
            System.out.println(Arrays.toString(num));
        }
    }

### 9.2.4 其他排序

希尔排序（shell），归并排序，快速排序等等...

# 10. Java对象

## 10.1 对象

万物皆对象

## 10.2 对象特征

>- 属性
>- 行为

## 10.3 面向过程

>- 开发时，分析问题的解决步骤，再调用方法步步解决

优点：执行时间短，效率高

缺点：代码不能复用

## 10.4 面向对象

>- 开发时：分析问题的具体实现对象是"谁"，而不考虑具体实现过程

优点：代码可复用

缺点：执行时间长，效率低

# 11. Java类

## 11.1 类

>- public class 类名
>- 通过成员变量来表示对象
>- 通过定义方法来表示对象的行为

## 11.2 类的使用

对象是类的实例化

一个类实例化多个对象

>- 类型 对象名称=new 类型();   //创建一个对象
>- 对象.成员变量=数据;   //赋值
>    类型 变量名称=对象.成员变量;    //获取值
>    对象.方法名称(实际参数);    //对象调用带参数的方法
>    对象.方法名称();    //对象调用不带参数的方法


## 11.3 细节

实例化方法（没有static修饰）和类方法（被static修饰）

>- 类方法可以直接通过类调用，也可以通过对象调用
>- 实例化方法必须通过对象调用

## 11.4 成员变量

>- 类变量可以直接通过类调用，也可以通过对象调用
>- 实例化变量必须通过对象调用

## 11.5 成员变量和局部变量的区别

### 11.5.1 成员变量

成员变量定义在类的内部，方法外部

成员变量都有默认值

>- 字符类型，默认值''（空字符）

成员变量不允许重名

内存中的位置：堆内存

### 11.5.2 局部变量

局部变量定义在方法内部

局部变量没有默认值

局部变量在不同方法内部可以重名

内存中的位置：栈内存

成员变量和局部变量可以重名，在使用时，遵循就近原则

## 11.6 构造方法

>- 类型 对象名称=new 类型();
>- 类型()，其实就是构造方法

# 12. Java封装

## 12.1 封装概述

在面向对象程式设计方法中，封装是指一种将抽象性函式接口的实现细节部分包装、隐藏起来的方法。

封装可以被认为是一个保护屏障，防止该类的代码和数据被外部类定义的代码随机访问。

要访问该类的代码和数据，必须通过严格的接口控制。

封装最主要的功能在于我们能修改自己的实现代码，而不用修改那些调用我们代码的程序片段。

适当的封装可以让程式码更容易理解与维护，也加强了程式码的安全性。

## 12.2 封装的优点

>- 良好的封装能够减少耦合。

>- 类内部的结构可以自由修改。

>- 可以对成员变量进行更精确的控制。

>- 隐藏信息，实现细节。

# 13. Getter&&Setter

getter方法：获取对应属性的属性值

setter方法：对对应属性值进行修改

# 14. 抽象

通过隐藏不必要的细节，降低外部调用的复杂度

如果一个方法使用 abstract 来修饰，则说明该方法是抽象方法，抽象方法只有声明没有实现。

需要注意的是 abstract 关键字只能用于普通方法，不能用于 static 方法或者构造方法中。

## 14.1 定义和使用规则

>- 抽象类和抽象方法都要使用 abstract 关键字声明。
>- 如果一个方法被声明为抽象的，那么这个类也必须声明为抽象的。
>- 而一个抽象类中，可以有任意个抽象方法，以及任意个具体方法。
>- 抽象类不能实例化，也就是不能使用 new 关键字创建对象。

## 14.2 抽象方法的特征

>- 抽象方法没有方法体
>- 抽象方法必须存在于抽象类中
>- 子类重写父类时，必须重写父类所有的抽象方法

## 14.3 注意：

在使用 abstract 关键字修饰抽象方法时不能使用 private 修饰
因为抽象方法必须被子类重写，而如果使用了 private 声明，则子类是无法重写的。

# 15. 耦合度

## 15.1 概述

耦合度(Coupling)是对模块间关联程度的度量。
耦合的强弱取决与模块间接口的复杂性。
调用模块的方式以及通过界面传送数据的多少。
模块间的耦合度是指模块之间的依赖关系，包括控制关系、调用关系、数据传递关系，模块间联系越多，其耦合性越强，同时表明其独立性越差。

## 15.2 设计原则

软件工程规定写代码的原则是“高内聚，低耦合”。
内聚是代码块间的独立性，耦合是各个代码块间的联系。

## 15.3 高耦合的缺点

>- 连锁反应，修改一个模块，多个模块都需要进行修改
>- 由于模块之间的相依性，模块的组合会需要更多的精力及时间

# 16. 构造器

构造器是一个类中的特殊方法，是用来构造和创建一个新对象的。

## 16.1 默认值

因为没有参数，所以类中的属性在初始化时将会设置为默认值

>- 数字初始化为0
>- 布尔类型初始化为false
>- 引用类型初始化为null

## 16.2 特点

>- 方法名与类名完全一致
>- 方法没有显式的返回值
>- 一旦定义了有参构造器，JVM将不会创建无参构造器（默认构造器）

# 17. Java继承

## 17.1 继承

在我们使用class来定义对象的时候
我们经常会发现很多对象之间又一些公共、基础的属性或行为

- 所有的UI控件（输入框、多选、单选、下拉框）都可以禁用，都有宽高
- 哺乳动物，都有身高、体重、血型等

我们在定义这些类的时候，并不想在所有的类中都定义重复的属性或者行为，那么就可以使用继承这种语法来重用代码。

我们可以把这些通用、公共的属性和行为定义在一个类中，这个类成为父类（parent） / 基类（base） / 超类（super），然后在定义子类（child/sub）来继承它。

## 17.2 继承类型

![logo](javaInherit.png)

## 17.3 继承特点

子类拥有父类非private的属性、方法。

子类可以拥有自己的属性和方法，即子类可以对父类进行扩展。

子类可以用自己的方式实现父类的方法。

提高了类之间的耦合性
（继承的缺点，耦合度高就会造成代码之间的联系越紧密，代码独立性越差）。

## 17.4 extends关键字

在 Java 中，类的继承是单一继承

一个子类只能拥有一个父类，所以 extends 只能继承一个类。

## 17.5 super 与 this 关键字

### 17.5.1 super关键字

我们可以通过super关键字来实现对父类成员的访问，用来引用当前对象的父类。

### 17.5.2 this关键字

指向自己的引用

## 17.6 Object

Java 中，所有的类都直接或间接的继承自Object。
因此我们定义的类自然也从这个父类获得了如下方法：

>- hashCode：得到一个整数值，它是基于内存地址运算出来的
>- equals：用来比较两个对象是否相等。
>- toString：对象的字符串表现形式

## 17.7 方法重写

在子类中如果创建了一个与父类中相同名称、相同返回值类型、相同参数列表的方法
只是方法体中的实现不同，以实现不同于父类的功能，这种方式被称为方法重写

### 17.7.1 重写规则

>- 参数列表必须与被重写的方法参数列表相同
>- 返回类型必须与被重写的方法返回类型相同
>- 访问权限不能比父类中被重写方法的访问权限更低
>- 父类的成员方法只能被它的子类重写
>- 声明为 final 的方法不能被重写
>- 声明为 static 的方法不能被重写
>- 构造方法不能被重写

## 17.8 向上&向下转型

>- UpCasting：向上转换成父类类型
>- DownCasting：向下转换成子类类型

## 17.9 多态

多种形态或形式，即允许一个对象有多种体现形式。

同一个行为，在不同的条件下，有不同的效果

## 18 接口




## 异常

## Throwable

>- getMessage()：返回此 throwable 的详细消息字符串
>- toString()：获取异常类名和异常信息
>- printStackTrace()：获取异常类名和异常信息，以及异常出现在程序中的位置
>- printStackTrace(PrintStream s)：通常用该方法将异常内容保存在日志文件中，以便查阅

## Exception 

### RuntimeException

不受检测的异常（不太严重的问题），就算有这种发生问题的可能性，既不要try-catch，也不要throws

### 非RuntimeExcetion

受检测的异常（较为严重的问题）

>- 自己来处理，编写try-catch
>- 自己不处理，在方法上添加throws xxException

## Error

程序猿无法解决的

## 注意事项

>- try 代码块越少越好
>- try 代码块出现异常，则不会执行后续代码
>- try-catch-finally finally修饰的代码块一定会执行