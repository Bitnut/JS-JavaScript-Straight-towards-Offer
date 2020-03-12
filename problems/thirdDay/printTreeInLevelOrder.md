# 题目地址

[https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/)

# 题目描述
从上到下打印出二叉树的每个节点，同一层的节点按照从左到右的顺序打印。

 

例如:
给定二叉树: [3,9,20,null,null,15,7],

    3
   / \
  9  20
    /  \
   15   7
返回：

[3,9,20,15,7]
 

提示：

节点总数 <= 1000

# 思路

# 关键点分析

# 代码
    var levelOrder = function(root) {
        let queue = [];
        let res = [];
        queue.push(root);
        if(!root) return [];
        while(queue.length !== 0) {
            let temp = queue.shift();
            res.push(temp.val);
            if(temp.left) {
                queue.push(temp.left);
                
            }
            if(temp.right) {
                queue.push(temp.right);
            }
        }
        return res;
        
    };
## [返回题目列表](../../README.md)