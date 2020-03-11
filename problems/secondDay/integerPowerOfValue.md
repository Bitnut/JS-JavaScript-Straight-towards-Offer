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