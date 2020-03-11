# 题目地址

[https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/](https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/)

# 题目描述
请实现一个函数，把字符串 s 中的每个空格替换成"%20"。

 

示例 1：

输入：s = "We are happy."
输出："We%20are%20happy."
 

限制：

0 <= s 的长度 <= 10000

# 思路

# 关键点分析

# 代码

    var replaceSpace = function(s) {
        var res = "";
        for(var i = 0; i<s.length; i++) {
            if(s[i] == ' ') {
                res +="%20";
            }
            else    res+=s[i];
        }
        return res;
    };

或者知道 replace 函数的也可以：

    var replaceSpace = function(s) {
        return s.replace(/\s/g, '%20');
    };