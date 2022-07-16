# JavaArraysTools
[Java](/back/javaREADME)

## "遍历"数组的方法

    Arrays类定义方法
    toString(类型[] 数组名称);

## Arrays排序(底层使用快速排序算法)

    Arrays类定义方法
    sort(类型[] 数组名称);
    sort(T[] a,Comparator<? super T> c);
    //根据对象里的数值属性进行排序，在排序时指定Comparator

## 比较

    Arrays
    static boolean equals(类型[] 数组名称,类型[] 数组名称)

## 将数组转成集合

    static <T> List<T> asList(T... a);
    //a为可变参数，其实就是数组，将数组转换成集合
