# 题目地址

[https://leetcode-cn.com/problems/shan-chu-lian-biao-de-jie-dian-lcof/](https://leetcode-cn.com/problems/shan-chu-lian-biao-de-jie-dian-lcof/)

# 题目描述
给定单向链表的头指针和一个要删除的节点的值，定义一个函数删除该节点。

返回删除后的链表的头节点。

注意：此题对比原题有改动

示例 1:

输入: head = [4,5,1,9], val = 5
输出: [4,1,9]
解释: 给定你链表中值为 5 的第二个节点，那么在调用了你的函数之后，该链表应变为 4 -> 1 -> 9.
示例 2:

输入: head = [4,5,1,9], val = 1
输出: [4,5,9]
解释: 给定你链表中值为 1 的第三个节点，那么在调用了你的函数之后，该链表应变为 4 -> 5 -> 9.
 

说明：

题目保证链表中节点的值互不相同
若使用 C 或 C++ 语言，你不需要 free 或 delete 被删除的节点

# 思路
删除链表节点，如果思路不清晰，最好画一张图。关键在于，找到该值的位置后，用一个临时变量拿到该节点下一个节点的引用，并将这个引用赋值给该节点的上一个节点。
# 关键点分析

# 代码
    var deleteNode = function(head, val) {
        let h = head;
        if(head.val === val) {
            head = head.next;
            return head;
        }
        while(h) {
            if(h.next.val === val) {
                let temp = h.next.next;
                h.next = temp;
                return head;

            } else {
                h = h.next;
            }
        }
    };
## [返回题目列表](../../README.md)