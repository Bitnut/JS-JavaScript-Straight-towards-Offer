# 题目地址

[https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)

# 题目描述
请完成一个函数，输入一个二叉树，该函数输出它的镜像。

例如输入：

     4
   /   \
  2     7
 / \   / \
1   3 6   9
镜像输出：

     4
   /   \
  7     2
 / \   / \
9   6 3   1

 

示例 1：

输入：root = [4,2,7,1,3,6,9]
输出：[4,7,2,9,6,3,1]
 

限制：

0 <= 节点个数 <= 1000

# 思路

# 关键点分析

# 代码
    var mirrorTree = function(root) {
        let temp;
        if(!root) return null;
        temp = root.left;
        root.left = root.right;
        root.right = temp; 
        mirrorTree(root.left);
        mirrorTree(root.right);

        return root;
    };
## [返回题目列表](../../README.md)