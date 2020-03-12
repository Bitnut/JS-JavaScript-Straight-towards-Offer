# 题目地址

[https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/](https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/)

# 题目描述
定义一个函数，输入一个链表的头节点，反转该链表并输出反转后链表的头节点。

 

示例:

输入: 1->2->3->4->5->NULL
输出: 5->4->3->2->1->NULL
 

限制：

0 <= 节点个数 <= 5000

# 思路
典型双指针问题，前后指针注意规范职责，可以借助适当画图明确思路。
# 关键点分析

# 代码
    var reverseList = function(head) {
        if(!head) return head;
        let pre = head.next;
        let cur = head;
        cur.next = null;
        while(pre) {
            temp = pre.next;
            pre.next = cur;
            cur = pre;
            pre = temp;
        }
        return cur;
    };
## [返回题目列表](../../README.md)