# 题目地址

[https://leetcode-cn.com/problems/qing-wa-tiao-tai-jie-wen-ti-lcof/](https://leetcode-cn.com/problems/qing-wa-tiao-tai-jie-wen-ti-lcof/)

# 题目描述
一只青蛙一次可以跳上1级台阶，也可以跳上2级台阶。求该青蛙跳上一个 n 级的台阶总共有多少种跳法。

答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。

示例 1：

输入：n = 2
输出：2
示例 2：

输入：n = 7
输出：21
提示：

0 <= n <= 100

# 思路
实际上就是斐波那契数列变形。关键在于先挑几个简单的例子试一下规律。
# 关键点分析

# 代码

    var numWays = function(n) {
        if(n === 0 )return 1;
        if(n === 1) return 1;
        if(n === 2) return 2;
        let sum = 0, a = 1, b = 2;
        for(var i = 2; i<n; i++) {
            sum = (a+b)%1000000007;
            a = b; 
            b = sum;
        }
        return sum;
    };
## [返回题目列表](../../README.md)