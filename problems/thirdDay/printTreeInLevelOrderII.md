# 题目地址

[https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-ii-lcof/](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-ii-lcof/)

# 题目描述
从上到下按层打印二叉树，同一层的节点按从左到右的顺序打印，每一层打印到一行。

 

例如:
给定二叉树: [3,9,20,null,null,15,7],

    3
   / \
  9  20
    /  \
   15   7
返回其层次遍历结果：

[
  [3],
  [9,20],
  [15,7]
]
 

提示：

节点总数 <= 1000

# 思路

# 关键点分析

# 代码
    var levelOrder = function(root) {
        let queue = [root];
        let res = [];
        let count = 0;
        if(!root) return [];
        while(queue.length !== 0) {
            let size = queue.length;
            res[count] = [];
            for(let i = 0; i< size; i++) {
                let temp = queue.shift();
                res[count][i] = temp.val;
                if(temp.left) {
                    queue.push(temp.left);
                    
                }
                if(temp.right) {
                    queue.push(temp.right);
                }
            }
            count++;
        }
        return res;
        
    };
## [返回题目列表](../../README.md)