# 题目地址

[https://leetcode-cn.com/problems/dui-cheng-de-er-cha-shu-lcof/](https://leetcode-cn.com/problems/dui-cheng-de-er-cha-shu-lcof/)

# 题目描述
请实现一个函数，用来判断一棵二叉树是不是对称的。如果一棵二叉树和它的镜像一样，那么它是对称的。

例如，二叉树 [1,2,2,3,4,4,3] 是对称的。

    1
   / \
  2   2
 / \ / \
3  4 4  3
但是下面这个 [1,2,2,null,3,null,3] 则不是镜像对称的:

    1
   / \
  2   2
   \   \
   3    3

 

示例 1：

输入：root = [1,2,2,3,4,4,3]
输出：true
示例 2：

输入：root = [1,2,2,null,3,null,3]
输出：false
 

限制：

0 <= 节点个数 <= 1000

# 思路

# 关键点分析

# 代码
    var isSymmetric = function(root) {
        var recur = function(l, r) {
            if(!l&&!r) return true;
            if( !l || !r || l.val !== r.val) return false;
            return recur(l.left, r.right)&&recur(l.right, r.left);
        }
        return !root ? true : recur(root.left, root.right);
    };
## [返回题目列表](../../README.md)
