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

重构二叉树关键在于中序遍历。前中后序遍历的简单记法如下：
前序： 根左右
中序： 左根右
后序： 左右根

重构整棵树的过程简化为重构一个两层的简单子树，这个最小子问题需要一个根节点、一个左节点、一个右节点。它的过程是给父节点连接左右子节点。

推广到一个普遍的方法就是，向父节点返回左右子树。这个方法（函数）需要的就是左子树集合（或者右子树）集合的前序和中序排列。

# 关键点分析
划分区域是本题关键点。通过取前序排列的首项，可以获得根节点的值。然后取得根节点值在中序遍历中的下标。这样就可以在前序和中序排列中划分左右集合了。

# 代码

    var buildTree = function(preorder, inorder) {
        if(!preorder.length||!inorder.length) return null;
        let rootVal = preorder[0];
        let root = new TreeNode(rootVal);
        let i = inorder.indexOf(rootVal);
        root.left = buildTree(preorder.slice(1, i+1), inorder.slice(0,i)); //细节： slice方法的用法：
        root.right = buildTree(preorder.slice(i+1), inorder.slice(i+1));   //传递i，j两个参数，返回下标范围[i,j-1]
        return root;                                                       //传递一个参数i，返回下标范围[i,末尾]
    };

## [返回题目列表](../../README.md)