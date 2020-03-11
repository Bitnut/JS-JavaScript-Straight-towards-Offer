# 题目地址

[https://leetcode-cn.com/problems/zhong-jian-er-cha-shu-lcof/](https://leetcode-cn.com/problems/zhong-jian-er-cha-shu-lcof/)

# 题目描述
输入某二叉树的前序遍历和中序遍历的结果，请重建该二叉树。假设输入的前序遍历和中序遍历的结果中都不含重复的数字。

 

例如，给出

前序遍历 preorder = [3,9,20,15,7]
中序遍历 inorder = [9,3,15,20,7]
返回如下的二叉树：

    3
   / \
  9  20
    /  \
   15   7
 

限制：

0 <= 节点个数 <= 5000

# 思路

# 关键点分析

# 代码

    var buildTree = function(preorder, inorder) {
        if(!preorder.length||!inorder.length) return null;
        let rootVal = preorder[0];
        let root = new TreeNode(rootVal);
        let i = inorder.indexOf(rootVal);
        root.left = buildTree(preorder.slice(1, i+1), inorder.slice(0,i));
        root.right = buildTree(preorder.slice(i+1), inorder.slice(i+1));
        return root;
    };