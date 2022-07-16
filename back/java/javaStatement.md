# Java语句
[Java](/back/java/README)

## IDEA

IDE:集成开发环境（IDE，Integrated Development Environment ）是用于提供程序开发环境的应用程序 

psvm:public static void main(String[] args){}

sout:System.out.println();

(Scanner方法名).nextLine().var

project和module

project包含module

## 流程语句

顺序，分支（比较，逻辑表达式），循环

nextLine():一行字符串

### if、if else

### Scanner

### switch(常量表达式)

常量表达式数据类型:

- 整数类型byte,short,int
- 字符类型:char
- 枚举类型:enum JDK1.5之后支持
- 字符串类型:String JDK7之后支持


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

- num=1或2或3,则都执行System.out.println("123");
