# 题目地址

[https://leetcode-cn.com/problems/fu-za-lian-biao-de-fu-zhi-lcof/](https://leetcode-cn.com/problems/fu-za-lian-biao-de-fu-zhi-lcof/)

# 题目描述
请实现 copyRandomList 函数，复制一个复杂链表。在复杂链表中，每个节点除了有一个 next 指针指向下一个节点，还有一个 random 指针指向链表中的任意节点或者 null。

 

示例 1：



输入：head = [[7,null],[13,0],[11,4],[10,2],[1,0]]
输出：[[7,null],[13,0],[11,4],[10,2],[1,0]]
示例 2：



输入：head = [[1,1],[2,1]]
输出：[[1,1],[2,1]]
示例 3：



输入：head = [[3,null],[3,0],[3,null]]
输出：[[3,null],[3,0],[3,null]]
示例 4：

输入：head = []
输出：[]
解释：给定的链表为空（空指针），因此返回 null。
 

提示：

-10000 <= Node.val <= 10000
Node.random 为空（null）或指向链表中的节点。
节点数目不超过 1000 。


# 思路

# 关键点分析

# 代码
C++

    #include <unordered_map>
    class Solution {
    public:
        Node* copyRandomList(Node* head) {
            unordered_map<Node*, Node*> mp;
            for(auto it = head; it; it = it->next){
                mp[it] = new Node(it->val);
            }
            for(auto it = head; it; it = it->next) {
                if(it->next) {mp[it]->next = mp[it->next];}
                if(it->random) {mp[it]->random = mp[it->random];}
            }
            return mp[head];
        }
    };
## [返回题目列表](../../README.md)