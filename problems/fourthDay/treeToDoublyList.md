# 题目地址

[https://leetcode-cn.com/problems/er-cha-sou-suo-shu-yu-shuang-xiang-lian-biao-lcof/](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-yu-shuang-xiang-lian-biao-lcof/)

# 题目描述
输入一棵二叉搜索树，将该二叉搜索树转换成一个排序的循环双向链表。要求不能创建任何新的节点，只能调整树中节点指针的指向。

 

为了让您更好地理解问题，以下面的二叉搜索树为例：

 



 

我们希望将这个二叉搜索树转化为双向循环链表。链表中的每个节点都有一个前驱和后继指针。对于双向循环链表，第一个节点的前驱是最后一个节点，最后一个节点的后继是第一个节点。

下图展示了上面的二叉搜索树转化成的链表。“head” 表示指向链表中有最小元素的节点。

 



 

特别地，我们希望可以就地完成转换操作。当转化完成以后，树中节点的左指针需要指向前驱，树中节点的右指针需要指向后继。还需要返回链表中的第一个节点的指针。


# 思路
递归中序遍历的过程中修改指针，最后链接头尾。
# 关键点分析
关键在于想到操作的时间点在左递归之后，右递归之前。始终只需要更新前驱节点即可。
# 代码
JS

    var treeToDoublyList = function(root) {
        if(!root) return null;
        var head = pre = null;
        var dfs = function(cur) {
            if(!cur) return;
            dfs(cur.left);
            if(!pre) {
                head = cur;
                pre = cur;
            } else {
                pre.right = cur;
                cur.left = pre;
                pre = cur;
            }
            dfs(cur.right);
        }
        dfs(root);
        head.left = pre;
        pre.right = head;
        return head;
    };

C++

    class Solution {
    public:
        Node* head, *pre;
        Node* treeToDoublyList(Node* root) {
            if(!root) return nullptr;
            head = nullptr;
            dfs(root);
            head->left = pre;
            pre->right = head;
            return head;
        }
        void dfs(Node* cur) {
            if(!cur) return;
            dfs(cur->left);
            if(!pre) {
                head = cur;
                pre = cur;
            } else {
                pre->right = cur;
                cur->left = pre;
                pre = cur;
            }
            dfs(cur->right);

        }
    };
## [返回题目列表](../../README.md)