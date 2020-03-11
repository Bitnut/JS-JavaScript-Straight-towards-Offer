# 题目地址

[https://leetcode-cn.com/problems/jian-sheng-zi-lcof/](https://leetcode-cn.com/problems/jian-sheng-zi-lcof/)

# 题目描述
给你一根长度为 n 的绳子，请把绳子剪成整数长度的 m 段（m、n都是整数，n>1并且m>1），每段绳子的长度记为 k[0],k[1]...k[m] 。请问 k[0]*k[1]*...*k[m] 可能的最大乘积是多少？例如，当绳子的长度是8时，我们把它剪成长度分别为2、3、3的三段，此时得到的最大乘积是18。

示例 1：

输入: 2
输出: 1
解释: 2 = 1 + 1, 1 × 1 = 1
示例 2:

输入: 10
输出: 36
解释: 10 = 3 + 3 + 4, 3 × 3 × 4 = 36
提示：

2 <= n <= 58

# 思路

# 关键点分析

# 代码    
    
    
    var cuttingRope = function(n) {
        if(n === 2) return 1;
        if(n === 3) return 2;
        let a = Math.floor(n/3);
        let b = n%3;
        if(b === 0) {
            return Math.pow(3,a);
        } else if(b === 1) {
            return Math.pow(3,a-1)*4;
        } else {
            return Math.pow(3,a)*2;
        }
    };

## [返回题目列表](../../README.md)