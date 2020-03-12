# 题目地址

[https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/](https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/)

# 题目描述
输入一个链表的头节点，从尾到头反过来返回每个节点的值（用数组返回）。

 

示例 1：

输入：head = [1,3,2]
输出：[2,3,1]
 

限制：

0 <= 链表长度 <= 10000

# 思路
直接遍历链表，将节点值按顺序存储在数组中，最后用reverse()将数组反转。
# 关键点分析

# 代码
    
    var reversePrint = function(head) {
        if(!head) return [];
        let res = [];
        while(head) {
            res.push(head.val);
            head = head.next;
        } 
        return res.reverse();
    };

## [返回题目列表](../../README.md)