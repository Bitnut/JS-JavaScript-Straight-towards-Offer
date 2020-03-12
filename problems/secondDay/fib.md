# 题目地址

[https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/](https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/)

# 题目描述
写一个函数，输入 n ，求斐波那契（Fibonacci）数列的第 n 项。斐波那契数列的定义如下：

F(0) = 0,   F(1) = 1
F(N) = F(N - 1) + F(N - 2), 其中 N > 1.
斐波那契数列由 0 和 1 开始，之后的斐波那契数就是由之前的两数相加而得出。

答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。

 

示例 1：

输入：n = 2
输出：1
示例 2：

输入：n = 5
输出：5
 

提示：

0 <= n <= 100

# 思路
斐波那契，注意用动态规划的优势 ———— 用恰当的数据结构存储小问题答案，这里用的是数组。单纯的递归会使得提交不通过。
另一种方式是直接按照数列的递推公式写出函数，这被称作迭代的方法。其实也算是一种动态规划。

# 关键点分析

# 代码

    var fib = function(n) {
        if(n<0) return false;
        if(n===0) {
            return 0;
        } else if (n===1) {
            return 1;
        }
        return (fib(n-1) + fib(n-2))%1000000007;
    };

    var fib = function(n) {
        if(n<0) return false;
        if(n===0) {
            return 0;
        } else if (n===1) {
            return 1;
        }
        let a = 0,b = 1,sum=0;
        for(let i = 0; i<n; i++){
            sum = (a+b)%1000000007;
            a = b;
            b = sum;
        }
        return a;
    };

## [返回题目列表](../../README.md)