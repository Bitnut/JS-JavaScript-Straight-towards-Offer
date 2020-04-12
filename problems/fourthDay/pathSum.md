# 题目地址

[https://leetcode-cn.com/problems/er-cha-shu-zhong-he-wei-mou-yi-zhi-de-lu-jing-lcof/](https://leetcode-cn.com/problems/er-cha-shu-zhong-he-wei-mou-yi-zhi-de-lu-jing-lcof/)

# 题目描述
输入一棵二叉树和一个整数，打印出二叉树中节点值的和为输入整数的所有路径。从树的根节点开始往下一直到叶节点所经过的节点形成一条路径。

 

示例:
给定如下二叉树，以及目标和 sum = 22，

              5
             / \
            4   8
           /   / \
          11  13  4
         /  \    / \
        7    2  5   1
返回:

[
   [5,4,11,2],
   [5,8,4,5]
]
 

提示：

节点总数 <= 10000

# 思路
递归这棵树，用tmp跟踪存储当前路径的数值，记得最后pop掉，用list或者vector容器都可以
# 关键点分析
注意这里JS传递的是数组的引用，传值进结果的时候注意深拷贝！！
# 代码
JS

    var pathSum = function(root, sum) {
        let res = [];
        let tmp = [];
        var iteration = function(root, target) {
            if(!root) return;
            if(!root.left&&!root.right) {
                if(target === root.val) {
                    res.push([...tmp, root.val]);// 这里深拷贝了！
                    return;
                } else return;
            }
            tmp.push(root.val);
            iteration(root.left, target - root.val);
            iteration(root.right, target - root.val);
            tmp.pop();
        }
        iteration(root, sum);
        return res;
    };

C++

    class Solution {
    public:
        vector<vector<int>> pathSum(TreeNode* root, int sum) {
            vector<vector<int>> res;
            vector<int> tmp;
            iteration(root, sum, tmp, res);
            return res;
        }
        void iteration(TreeNode* root, int target, vector<int>& tmp, vector<vector<int>> &res) {
            if(root == NULL) return;
            if(root->left==NULL&&root->right==NULL) {
                if(target==root->val) {
                    tmp.push_back(root->val);
                    res.push_back(tmp);
                    tmp.pop_back();
                    return;
                } else return;
            }
            tmp.push_back(root->val);
            iteration(root->left, target - root->val, tmp, res);
            iteration(root->right, target - root->val, tmp, res);
            tmp.pop_back();
            return;
        }
    };
## [返回题目列表](../../README.md)