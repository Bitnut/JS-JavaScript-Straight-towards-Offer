# 题目地址

[https://leetcode-cn.com/problems/biao-shi-shu-zhi-de-zi-fu-chuan-lcof/](https://leetcode-cn.com/problems/biao-shi-shu-zhi-de-zi-fu-chuan-lcof/)

# 题目描述

请实现一个函数用来判断字符串是否表示数值（包括整数和小数）。例如，字符串"+100"、"5e2"、"-123"、"3.1416"、"0123"及"-1E-16"都表示数值，但"12e"、"1a3.14"、"1.2.3"、"+-5"及"12e+5.4"都不是。


# 思路

直接用强制转换做了，有点像脑筋急转弯。。。

# 关键点分析

# 代码
    //这题有点莫名其妙。。。
    var isNumber = function(s) {
        if(s === " ") return false;
        if(isNaN(s*1)) {
            return false;
        } else return true;
    };
## [返回题目列表](../../README.md)