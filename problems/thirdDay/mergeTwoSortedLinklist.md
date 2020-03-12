# 题目地址

[https://leetcode-cn.com/problems/he-bing-liang-ge-pai-xu-de-lian-biao-lcof/](https://leetcode-cn.com/problems/he-bing-liang-ge-pai-xu-de-lian-biao-lcof/)

# 题目描述
输入两个递增排序的链表，合并这两个链表并使新链表中的节点仍然是递增排序的。

示例1：

输入：1->2->4, 1->3->4
输出：1->1->2->3->4->4
限制：

0 <= 链表长度 <= 1000


# 思路

# 关键点分析

# 代码
    var mergeTwoLists = function(l1, l2) {
        let res = new ListNode();
        let cur = res;
        while(l1 && l2) {
            if (l1.val < l2.val) {
                cur.next = l1
                cur = cur.next;
                l1 = l1.next;
                
            } else {
                cur.next = l2;
                cur = cur.next;
                l2 = l2.next;
            }
        }
        cur.next = l1 ? l1 : l2;
        return res.next;
    };
## [返回题目列表](../../README.md)