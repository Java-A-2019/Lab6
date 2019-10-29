# Lab6
放心这次一定简单！<br/>
这次Lab主要教大家使用递归。<br/>
首先，请大家下载Lab6.zip，然后解压到本地，用IDEA打开。

## 什么是递归
> 假设你在一个电影院，你想知道自己坐在哪一排，但是前面人很多，你懒得去数了，于是你问前一排的人「你坐在哪一排？」，这样前面的人 (代号 A) 回答你以后，你就知道自己在哪一排了——只要把 A 的答案加一，就是自己所在的排了。不料 A 比你还懒，他也不想数，于是他也问他前面的人 B「你坐在哪一排？」，这样 A 可以用和你一模一样的步骤知道自己所在的排。然后 B 也如法炮制。直到他们这一串人问到了最前面的一排，第一排的人告诉问问题的人「我在第一排」。最后大家就都知道自己在哪一排了。 <br/>
—— 源自知乎Memoria

递归就是，创建一个function, 然后在function的内部再次调用本身。上个世纪七八十年代，技术和理论都不发达，大家用的也不是现在的高级编程语言，人们原本认为递归无法实现。它需要面对的难题是，计算机如果要调用一个方法，就首先要读取该方法的定义，可是它在读取该定义的时候，又要先调用该方法。后来，某位科学家证明并实现了递归（忘记是谁了），从而引发了编程语言的一场革命。所以，学习一下递归，缓解一下大家的压力，还是蛮有必要的。

## 一个简单的栗子
我们首先有如下的函数定义：
```java
/**
* compute factorial
* @param n compute factorial of n
* @return int return factorial of n
* */
public static int factorial(int n)
```
这函数会计算 n! = n * (n-1) * (n-2) * ... * 1。
当然我们还有另外一个公式 n!= n * (n-1)!
相信这理解起来不会有什么困难。

```java
public static int factorial(int n) {
    return n * factorial(n-1);
}
```
但是这个函数存在问题，缺乏终止条件。比如当n == 0 的时候，就应该返回，否则，这个function将持续调用自己，知道系统内存崩溃。
```java
public static int factorial(int n) {
    if (n <= 1) return 1;
    return n * factorial(n-1);
}
```
我们可以稍微做一下总结，
1. 递归要调用自身。可以解决存在相同子结构的问题。
2. 递归需要终止条件。

递归的好处是明显的，相对于循环，它可以简化问题，减少思考量。当它应用于数据结构的分治思想时，它能够发挥更大的作用。

## 下一个栗子 - 泰波那契数
由于斐波那契数的计算量太小了，所以我们引入了泰波那契数。
泰波那契序列 Tn 定义如下： 
<img src="http://chart.googleapis.com/chart?cht=tx&chl= $$T_0$$ = 0,$$T_1$$ = 1, $$T_2$$ = 1" style="border:none;">
且在 n >= 0 的条件下 
<img src="http://chart.googleapis.com/chart?cht=tx&chl= $$T_{n+3}$$ = $$T_n$$ + $$T_{n+1}$$ + $$T_{n+2}$$" style="border:none;">

### 问题
给你整数 n，请返回第 n 个泰波那契数 Tn 的值。

### 要求
1. 填写Tribonacci类的tribonacci方法，并跑通TribonacciTest的测试。追求难度的同学可以将测试数据改成test data 1! 想要跑通test data 1 光靠蛮力计算是不行的，所以，想点办法咯 ^^
2. 将整个项目打包上传到ftp WORK_UPLOAD的lab6目录下，命名为学号+姓名，方便排序。（而不是姓名+学号）
3. 截止时间为2019年11月3日23点59分59秒。

### 注意
test如果出现了问题，请见IDEA中junit4简单使用 —— “划重点 ----- 如何处理这个报错！” ： https://blog.csdn.net/zhaoyangyingmu/article/details/102777789







