# 题目地址

[https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/](https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/)

# 题目描述

在一个 n * m 的二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。

 

示例:

现有矩阵 matrix 如下：

[
  [1,   4,  7, 11, 15],
  [2,   5,  8, 12, 19],
  [3,   6,  9, 16, 22],
  [10, 13, 14, 17, 24],
  [18, 21, 23, 26, 30]
]
给定 target = 5，返回 true。

给定 target = 20，返回 false。

 

限制：

0 <= n <= 1000

0 <= m <= 1000

# 思路

# 关键点分析

# 代码
    var findNumberIn2DArray = function(matrix, target) {
        if(!matrix || matrix.length === 0) return false;
        let col = 0, row = matrix.length -1;
        while(col <= matrix[0].length-1 && row >= 0){
            if(matrix[row][col]<target) {
                col++;
            } else if (matrix[row][col]>target) {
                row--;
            } else if (matrix[row][col] === target) {
                return true;
            }
        }
        return false;
    };

## [返回题目列表](../../README.md)