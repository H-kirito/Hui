# Java二维数组
[Java](/back/java/README)

## 二维数组

Java并不直接支持二维数组
但是允许定义数组元素是一维数组的一维数组，以达到同样的效果

type arrayName[][];   // 数据类型 数组名[][];
type[][] arrayName;   // 数据类型[][] 数组名;

type[][] arrayName = new type[][]{值1,值2,值3,…,值n};   // 在定义时初始化
type[][] arrayName = new type[size1][size2];   // 给定空间，在赋值
type[][] arrayName = new type[size][];   // 数组第二维长度为空，可变化

## 排序算法（大到小，小到大）

### 冒泡排序

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



### 选择排序

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



### 插入排序

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


### 其他排序
希尔排序（shell），归并排序，快速排序等等...






