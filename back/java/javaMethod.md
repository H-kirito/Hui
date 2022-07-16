# Java方法
[Java](/back/java/README)


## 方法(method,function)

- 解决代码冗余问题，可重复使用

- 方法的使用
  - 定义方法
  - 调用方法
      public static void 方法名(){ 
          方法体;
      }

## 方法的参数

- 形式参数
      public static void 方法名(类型 形参名){ 
          方法体;
      }
- 实际参数
      public static void main(String[] args) {
      	方法名(实参);//数据
      }



## return

- 返回值是通过关键字return实现的.
- 返回值类型一定和return后面的数据类型,一定保持一致.

1、返回方法指定类型的值（这个值总是确定的），也可以是对象

2、结束方法，终止“return;”后面代码的执行

## 方法的重载

- 方法名相同，方法参数不同
  方法名相同，方法参数类型不同	

## 可变参数

    public static 数据类型 add(int... params){
        //params(可变参数名称)
        //可变参数必须放参数列表最后
        方法体;
        return 数据;
    }



### 递归求阶乘

    public static int fact(int n){
        if(n == 1) 
            return 1;
        return fact(n-1) * n;
    } 



## 数组

### 数组特点

- 数组保存的数据类型相同
- 数组可保存多个数据
- 数组长度是固定的

### 数组创建

- 动态数组
- 静态数组

## 方法细节

### 成员变量

- 定义在方法外的变量
- 可不赋值，一般有默认值

### 局部变量

- 定义在方法内的变量

引用类型变量没赋值，默认为null

方法的参数为基本类型，会在栈内存中执行

方法的参数为引用类型，数据会在堆空间保存






