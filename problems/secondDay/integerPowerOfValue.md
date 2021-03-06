# 题目地址

[https://leetcode-cn.com/problems/shu-zhi-de-zheng-shu-ci-fang-lcof/](https://leetcode-cn.com/problems/shu-zhi-de-zheng-shu-ci-fang-lcof/)

# 题目描述
实现函数double Power(double base, int exponent)，求base的exponent次方。不得使用库函数，同时不需要考虑大数问题。

 

示例 1:

输入: 2.00000, 10
输出: 1024.00000
示例 2:

输入: 2.10000, 3
输出: 9.26100
示例 3:

输入: 2.00000, -2
输出: 0.25000
解释: 2-2 = 1/22 = 1/4 = 0.25
 

说明:

-100.0 < x < 100.0
n 是 32 位有符号整数，其数值范围是 [−231, 231 − 1] 。

# 思路
直接使用循环作乘法会使得某些极端的例子无法通过，这道题目考察的是数学问题。

例如二进制数： 1001，可以看做是2^0+2^3，x^9 = (x^0\*1)\*(x^8*1);可以看到随着数位向高位推进（n&1 并移位方法），x的指数幂也以2^n次方的形式增加。

因此在循环中，若该位为1，则结果\*x，若为0，则什么都不做。每次基数x需要自乘。这样的话减少了大量乘以原始x的运算次数，算法效率数量级提升。

# 关键点分析

# 代码
    var myPow = function(x, n) {
        if(x===0) return 0;
        if(n===0) return 1;
        flag = 0;
        if(n<0) {
            flag = 1;
            n= Math.abs(n);
        }
        res = 1;
        while(n) {
            if(n&1) {res = res*x;}
            x = x*x;
            n = Math.floor(n/2);
        }
        return flag?1/res:res;
    };
## [返回题目列表](../../README.md)