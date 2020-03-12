# 题目地址

[https://leetcode-cn.com/problems/lian-biao-zhong-dao-shu-di-kge-jie-dian-lcof/](https://leetcode-cn.com/problems/lian-biao-zhong-dao-shu-di-kge-jie-dian-lcof/)

# 题目描述
输入一个链表，输出该链表中倒数第k个节点。为了符合大多数人的习惯，本题从1开始计数，即链表的尾节点是倒数第1个节点。例如，一个链表有6个节点，从头节点开始，它们的值依次是1、2、3、4、5、6。这个链表的倒数第3个节点是值为4的节点。

 

示例：

给定一个链表: 1->2->3->4->5, 和 k = 2.

返回链表 4->5.

# 思路

典型双指针问题，先让快指针跑，然后慢指针和快指针同时向后遍历链表，直到快指针为null跳出循环。返回慢指针即可。

# 关键点分析

# 代码
    var getKthFromEnd = function(head, k) {
        let fast = head, slow = head;
        for(let i = 0 ; i < k; i++) {
            fast = fast.next;
            
        }
        while(fast) {
            fast = fast.next;
            slow = slow.next;
        }
        return slow;
    };
## [返回题目列表](../../README.md)