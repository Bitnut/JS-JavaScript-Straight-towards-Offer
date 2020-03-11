# 题目地址

[https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/](https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/)

# 题目描述
输入数字 n，按顺序打印出从 1 到最大的 n 位十进制数。比如输入 3，则打印出 1、2、3 一直到最大的 3 位数 999。

示例 1:

输入: n = 1
输出: [1,2,3,4,5,6,7,8,9]
 

说明：

用返回一个整数列表来代替打印
n 为正整数

# 思路

# 关键点分析

# 代码
    var printNumbers = function(n) {
        let ceiling = Math.pow(10,n);
        let res = []
        for(let i = 0; i< ceiling-1; i++) {
            res[i] = i+1;
        }
        return res;
    };
## [返回题目列表](../../README.md)