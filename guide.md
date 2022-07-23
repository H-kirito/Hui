新页面

>- 用来整理学习中创建的有代表意义的项目

[<<返回首页](/README)

## 随机生成大小写字母

~~~java
import java.util.Random;

public static String randomString(){
    Random randomAlphabet = new Random();
    if(randomAlphabet.nextInt(2)%2==0){//如果随机数为0则随机生成大写字母，为1则随机生成小写字母
        char alphabetUpper= (char)(randomAlphabet.nextInt(26)+65);
        String a=String.valueOf(alphabetUpper);
        //System.out.println(alphabetUpper);//输出大写字母
        return a;
    }else {
        char alphabetLower = (char) (randomAlphabet.nextInt(26) + 97);
        String b=String.valueOf(alphabetLower);
        //System.out.println(alphabetLower);//输出小写字母
        return b;
    }
}
~~~

>- 可改写成用户输入0随机生成大写字母/输入1随机生成小写字母

~~~java
import java.util.Random;
import java.util.Scanner;

public static void randomString() {
        Random randomAlphabet = new Random();
        Scanner sc = new Scanner(System.in);
        System.out.println("========菜单========");
        System.out.println("0，随机生成大写字母");
        System.out.println("1，随机生成小写字母");
        System.out.println("2，退出程序");
        System.out.println("===================");
        //如果为0则随机生成大写字母，为1则随机生成小写字母
        int num = sc.nextInt();
        if (num == 0) {
            char alphabetUpper = (char) (randomAlphabet.nextInt(26) + 65);
            System.out.println(alphabetUpper);//输出大写字母
            System.out.println();
            randomString();
        }
        if (num == 1) {
            char alphabetLower = (char) (randomAlphabet.nextInt(26) + 97);
            System.out.println(alphabetLower);//输出小写字母
            System.out.println();
            randomString();
        }
        if(num==2) return;//输入2则退出程序
        if(num!=0&&num!=1){
            System.out.println("输入有误，"+num+"不在选项内，请重新输入");
            System.out.println();
            randomString();
        }
    }
~~~

## io流

>- (字节流)利用FilelnputStream和FileOutputStream，完成下面的要求∶
>- 1、用FileOutputStream在当前目录下创建一个文件“test.txt”，
>- 并向文件输出“Hello World”，如果文件已存在，则在原有文件内容后面追加
>- 2、用FilelnputStream读入test.txt文件，并在控制台上打印出test.txt 中的内容
>- 3、要求用try-catch-finally处理异常，并且关闭流应放在finally块中

~~~java
import java.io.*;

public class FileInOutputStream {
    public static void main(String[] args) throws IOException {
        //在用户桌面创建一个test.txt文件
        String path = "C:\\Users\\Administrator\\Desktop\\test.txt";
        FileOutputStream fos = new FileOutputStream(path,true);
        FileInputStream fis = new FileInputStream(path);
        try {
            fos.write("Hello World".getBytes());
            int length = 0;
            //-1则说明没有剩余字节可取了
            while ((length = fis.read()) != -1) {
                System.out.print((char) length);
            }
        } catch (IOException e) {
            //throw new RuntimeException(e);
            e.printStackTrace();
        } finally {
            //关闭流
            fos.close();
            fis.close();
        }
    }
}
~~~

### 约瑟夫环问题

>- 有80个⼩朋友⼿拉⼿围成⼀圈，由第⼀个⼩朋友开始从1开始数,
>- 数到3的⼩朋友退出，再从后⾯的⼩朋友从1数起,
>- 数到3的再退出，以此游戏下去，问最后剩下哪个⼩朋友？(使⽤集合实现)

~~~java
package main.com.hui.game;

import java.util.Arrays;

public class Game {

    public static void main(String[] args) {
        initialize();
        gameStart();
        lastOneChild();
    }
    //创建一个数组
    private static final boolean[] arr = new boolean[80];
    private static void initialize(){
        //初始化小朋友的值为true
//        for (int i = 0; i < arr.length; i++) {
//            arr[i] = true;
//        }
        Arrays.fill(arr, true);
    }
    private static void lastOneChild(){
        for (int i = 0; i < arr.length; i++) {
            //最后只剩一个为true的小朋友
            //因为i从0开始，所以小朋友的位置应该为(i+1)
            if(arr[i]==true) System.out.println("最后剩下的小朋友为："+(i+1)+"个");
        }
    }

    private static void gameStart(){
        /*定义一个index，用来获取小朋友的数字
        定义一个count，用来统计剩余小朋友数量
        定义一个number，每叠加到3时则为0*/
         int index=0;
         int count = arr.length;
         int number=0;
        while(count>1){
            if (arr[index]==true){
                number++;
                if(number==3){
                    //当number=3时，为该位置小朋友赋值为false
                    arr[index]=false;
                    count--;
                    //重新开始计数
                    number=0;
                }
            }
            index++;
            //index为80说明已经进行了一次循环了，赋值为0进行下一次循环
            if(index==80){
                index=0;
            }
        }
    }
}
~~~

