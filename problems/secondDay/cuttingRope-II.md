# 题目地址

[https://leetcode-cn.com/problems/jian-sheng-zi-ii-lcof/submissions/](https://leetcode-cn.com/problems/jian-sheng-zi-ii-lcof/submissions/)

# 题目描述
给你一根长度为 n 的绳子，请把绳子剪成整数长度的 m 段（m、n都是整数，n>1并且m>1），每段绳子的长度记为 k[0],k[1]...k[m] 。请问 k[0]*k[1]*...*k[m] 可能的最大乘积是多少？例如，当绳子的长度是8时，我们把它剪成长度分别为2、3、3的三段，此时得到的最大乘积是18。

答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。

 

示例 1：

输入: 2
输出: 1
解释: 2 = 1 + 1, 1 × 1 = 1
示例 2:

输入: 10
输出: 36
解释: 10 = 3 + 3 + 4, 3 × 3 × 4 = 36
 

提示：

2 <= n <= 1000

# 思路
思路同上题，但是这里需要注意需要在中途运算的时候作取余运算，否则提交会错误。
# 关键点分析

# 代码
    var cuttingRope = function(n) {
        if(n === 2) return 1;
        if(n === 3) return 2;
        let a = Math.floor(n/3);
        let b = n%3;
        let res = 1;
        if(b === 1) {
            a--;
            b++;
        } else if (b === 2) {
            b--;
        }
        while(a--!==0) {
            res = (res*3)%1000000007;
        }
        while(b--!==0) {
            res = (res*2)%1000000007;
        }
        
        return res;
    };
## [返回题目列表](../../README.md)

