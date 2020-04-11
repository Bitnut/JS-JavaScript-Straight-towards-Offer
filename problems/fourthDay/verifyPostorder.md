# 题目地址

[https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-hou-xu-bian-li-xu-lie-lcof/](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-hou-xu-bian-li-xu-lie-lcof/)

# 题目描述
输入一个整数数组，判断该数组是不是某二叉搜索树的后序遍历结果。如果是则返回 true，否则返回 false。假设输入的数组的任意两个数字都互不相同。

 

参考以下这颗二叉搜索树：

        5
       / \
      2   6
     / \
    1   3

示例 1：

输入: [1,6,3,2,5]
输出: false
示例 2：

输入: [1,3,2,6,5]
输出: true
 

提示：

数组长度 <= 1000


# 思路
递归左右子树，仅需要遍历右子树内容，左子树为可靠子树。
# 关键点分析

# 代码
JS

    var verifyPostorder = function(postorder) {
        var iteration = function (l, r) {
            if( l >= r) return true;
            for(var i = l; i < r; i++) {//注意这里我希望i可以在for循环外使用
                if(postorder[i] > postorder[r]) break;
            }
            for(var j = i; j < r; j++) {
                if(postorder[j] < postorder[r]) return false;
            }
            return iteration(l, i - 1) && iteration(i, r - 1);
        }
        return iteration(0, postorder.length - 1);
    };

C++

    class Solution {
    public:
        bool verifyPostorder(vector<int>& postorder) {
            return iteration(postorder, 0, postorder.size() - 1);
        }
        bool iteration(vector<int> a, int l, int r) {
            if(l >= r) return true;
            int i;
            for(i = l; i < r; i++) {
                if(a[i] > a[r]) break;
            }
            for(int j = i; j < r; j++) {
                if(a[j] < a[r]) return false;
            }
            return iteration(a, l, i-1) && iteration(a, i, r-1);
        }
    };
    
## [返回题目列表](../../README.md)