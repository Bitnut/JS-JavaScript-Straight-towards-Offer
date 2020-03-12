# 题目地址

[https://leetcode-cn.com/problems/ji-qi-ren-de-yun-dong-fan-wei-lcof/](https://leetcode-cn.com/problems/ji-qi-ren-de-yun-dong-fan-wei-lcof/)

# 题目描述
地上有一个m行n列的方格，从坐标 [0,0] 到坐标 [m-1,n-1] 。一个机器人从坐标 [0, 0] 的格子开始移动，它每次可以向左、右、上、下移动一格（不能移动到方格外），也不能进入行坐标和列坐标的数位之和大于k的格子。例如，当k为18时，机器人能够进入方格 [35, 37] ，因为3+5+3+7=18。但它不能进入方格 [35, 38]，因为3+5+3+8=19。请问该机器人能够到达多少个格子？

 

示例 1：

输入：m = 2, n = 3, k = 1
输出：3
示例 1：

输入：m = 3, n = 1, k = 0
输出：1
提示：

1 <= n,m <= 100
0 <= k <= 20

# 思路

题目规定机器人只能向右或者向下走。

通过DFS遍历整个矩阵，用一个对象存储已经遍历过的位置。

用一个函数单独计算数位和，提升代码可读性。
# 关键点分析

由于只需要返回走得到的位置数目，当某个位置遍历过可以直接返回false。

# 代码

    var movingCount = function(m, n, k) {
        let count = 0;
        let hash = {};
        var DFS = function(row, col) {
            if(row>m-1||col>n-1||hash[`${row}-${col}`]) return false;
            let sum = sumData(row, col);
            if(sum > k) return false;
            count++;
            hash[`${row}-${col}`] = true;
            
            DFS(row+1, col);
            DFS(row, col+1);
        }
        let res = DFS(0, 0);
        return count;
    };

    var sumData = function(a, b) {
        let res = 0;
        while(a!==0) {
            res += a%10;
            a = Math.floor(a/10);
        }
        while(b!==0) {
            res += b%10;
            b = Math.floor(b/10);
        }
        return res;
    }
## [返回题目列表](../../README.md)