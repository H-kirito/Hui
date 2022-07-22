# 构造器
[Java](/back/java/README)

构造器是一个类中的特殊方法，是用来构造和创建一个新对象的。

## 默认值

因为没有参数，所以类中的属性在初始化时将会设置为默认值

>- 数字初始化为0
>- 布尔类型初始化为false
>- 引用类型初始化为null

## 特点

>- 方法名与类名完全一致
>- 方法没有显式的返回值
>- 一旦定义了有参构造器，JVM将不会创建无参构造器（默认构造器）