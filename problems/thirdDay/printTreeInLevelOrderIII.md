# 题目地址

[https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-iii-lcof/](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-iii-lcof/)

# 题目描述
请实现一个函数按照之字形顺序打印二叉树，即第一行按照从左到右的顺序打印，第二层按照从右到左的顺序打印，第三行再按照从左到右的顺序打印，其他行以此类推。

 

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
  [20,9],
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
            if(count % 2 === 0) {
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
            } else {
                for(let i = size-1; i >= 0; i--) {
                    let temp = queue.shift();
                    res[count][i] = temp.val;
                    if(temp.left) {
                        queue.push(temp.left);
                        
                    }
                    if(temp.right) {
                        queue.push(temp.right);
                    }
                }
            }
            
            count++;
        }
        return res;
    };
## [返回题目列表](../../README.md)