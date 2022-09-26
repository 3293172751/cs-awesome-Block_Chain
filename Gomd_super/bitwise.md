# 位运算

[toc]

## ℹ️前言

> + 参考文章：[https://gist.github.com/dideler/2365607](https://gist.github.com/dideler/2365607)、[https://us.com/](https://us.com/)
>
> + 推荐一个学习正则表达式的网站：[https://regexr.com/](https://regexr.com/)
>
> + 使用的环境：`Java – jshell`（因为`ipython`中不可以用`++i`）

**在[leetcode算法](http://github.com/3293172751/LeetCode)中我提到了很多关于位运算的技巧，进行了一次总结**



## 🎈乘以 2 的幂

```java
x = x << 1; // x = x * 2
x = x << 6; // x = x * 64
```

> 对于两个数`a`，`b`，计算`a` 和 b 的中间值，如果计算a+b除以2，可能会出现a+b溢出，所以你可以：
>
> ```java
> var c = ((b - a) >> 2) + a
> ```



## 🎈除以 2 的幂

```java
x = x >> 1; // x = x / 2
x = x >> 3; // x = x / 8
```



## 🎈交换没有临时变量的整数

```
a ^= b; // int temp = b
b ^= a; // b = a
a ^= b; // a = temp
```

![image-20220925161607882](http://sm.nsddd.top/smimage-20220925161607882.png?xxw@nsddd.top)



## 🎈增量/减量（较慢但有利于混淆）

```
i = -~i; // i++
i = ~-i; // i--
```

![image-20220925161741820](http://sm.nsddd.top/smimage-20220925161741820.png?xxw@nsddd.top)



## 🎈标志翻转

```java
i = ~i + 1; // or
i = (i ^ -1) + 1; // i = -i
```



## 🎈如果除数是 2 的幂，则进行模运算

```java
x = 131 & (4 - 1); // x = 131 % 4
```



## 🎈检查整数是偶数还是奇数

```java
(i & 1) == 0; // (i % 2) == 0
```



## 🎈相等检查

```java
(a^b) == 0; // a == b
```



## 🎈绝对值

```java
x < 0 ? -x : x; // abs(x)
(x ^ (x >> 31)) - (x >> 31) // abs(x)
```



## 🎈等号检查（两个整数都是 pos 或 neg）

```java
a ^ b >= 0; // a * b > 0
```



## 🎈圆角、天花板、地板

```java
(x + 0.5) >> 0; // round(x)
(x + 1) >> 0; // ceil(x)
x >> 0; // floor(x)
```