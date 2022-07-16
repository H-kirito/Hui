# Java循环
[Java](/back/javaR/EADME)

循环结构语句

## for

    for(初始化语句;条件判断语句;条件控制语句){
        循环体语句
    }

- 初始化语句
- 条件判断语句
- 条件控制语句
- 循环体语句

## while

    初始化语句;
    while(条件判断语句){
    	循环体语句;
        条件控制语句;
    }

## do while

    初始化语句;
    do{
    	循环体语句;
        条件控制语句;
    }while(条件判断语句);

- do while语句至少运行一次循环体

## break

- 循环语句中跳出循环

## continue

- 结束当前循环，进行下一次循环
- 只能用于循环

    for(int i=1;i<=5;i++){
        if(i==3)
            continue;
    	System.out.println(i);
    }

## Random

获取随机数

- 导入包
- 创建随机数对象
- 通过对象调用

    import java.util.Random;

    Random random=new Random();

    int randNumber=random.nextInt(bound:10);//[0,10)

### Guess数字

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

## 嵌套循环

### 九九乘法表

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

### 等腰三角形

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


