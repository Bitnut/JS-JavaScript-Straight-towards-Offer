# 题目地址

[https://leetcode-cn.com/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/](https://leetcode-cn.com/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/)

# 题目描述
输入一个矩阵，按照从外向里以顺时针的顺序依次打印出每一个数字。

 

示例 1：

输入：matrix = [[1,2,3],[4,5,6],[7,8,9]]
输出：[1,2,3,6,9,8,7,4,5]
示例 2：

输入：matrix = [[1,2,3,4],[5,6,7,8],[9,10,11,12]]
输出：[1,2,3,4,8,12,11,10,9,5,6,7]
 

限制：

0 <= matrix.length <= 100
0 <= matrix[i].length <= 100


# 思路

# 关键点分析

# 代码
    var spiralOrder = function(matrix) {
        if(!matrix.length) return matrix;
        let res = [];
        let cols = matrix[0].length;
        let rows = matrix.length-1;
        let count = cols*(rows+1);
        let row = col = 0;
        var dir = {
            up: false,
            down: false,
            left: false,
            right:true
        }
        while(count>0){
            if(dir.up) {
                for (let i = 0; i < rows; i++) {
                    res.push(matrix[row][col]);
                    row--;
                    count--;
                }
                row++;
                col++;
                rows--;
                dir.up = false;
                dir.right = true;
            } else if (dir.down) {
                for (let i = 0; i < rows; i++) {
                    res.push(matrix[row][col]);
                    row++;
                    count--;
                }
                row--;
                col--;
                rows--;
                dir.down = false;
                dir.left = true;
            } else if(dir.left) {
                for (let i = 0; i < cols; i++) {
                    res.push(matrix[row][col]);
                    col--;
                    count--;
                }
                col++;
                row--;
                cols--;
                dir.left = false;
                dir.up = true;
            } else if (dir.right) {
                for (let i = 0; i < cols; i++) {
                    res.push(matrix[row][col]);
                    col++;
                    count--;
                }
                col--;
                row++;
                cols--;
                dir.right = false;
                dir.down = true;
            }
        }
        return res;
    };
## [返回题目列表](../../README.md)