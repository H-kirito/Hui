# Java数组
[Java](/back/java/README)

## 数组创建

- 动态数组
  - 数据类型[] 数组名称=new 数据类型[长度];
- 静态数组
  - 数据类型[] 数组名称={x1,x2,x3};

索引

数组的取值，赋值

## 数组遍历

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
## 数组数据顺序调换
### 方法一
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
### 方法二
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
- 随机获取数组值


## JVM内存分配情况(浅谈)

- 栈内存 先进先出
- 堆内存
  保存引用类型对象
  当对象不被引用(指对象不再使用)，对象最终被java的GC回收


## 数组的扩容

扩容：改变数组的长度

分析：数组的长度是固定的，该如何扩容

思路：

	1.新建一个数组，指定扩容后的长度

	2.将原有数组的数据设置到新的数组里面

	3.将新建的数组再赋值给原有数组，完成原有数组的扩容
