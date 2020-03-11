# 题目地址

[https://leetcode-cn.com/problems/ju-zhen-zhong-de-lu-jing-lcof/](https://leetcode-cn.com/problems/ju-zhen-zhong-de-lu-jing-lcof/)

# 题目描述
请设计一个函数，用来判断在一个矩阵中是否存在一条包含某字符串所有字符的路径。路径可以从矩阵中的任意一格开始，每一步可以在矩阵中向左、右、上、下移动一格。如果一条路径经过了矩阵的某一格，那么该路径不能再次进入该格子。例如，在下面的3×4的矩阵中包含一条字符串“bfce”的路径（路径中的字母用加粗标出）。

[["a","b","c","e"],
["s","f","c","s"],
["a","d","e","e"]]

但矩阵中不包含字符串“abfb”的路径，因为字符串的第一个字符b占据了矩阵中的第一行第二个格子之后，路径不能再次进入这个格子。

 

示例 1：

输入：board = [["A","B","C","E"],["S","F","C","S"],["A","D","E","E"]], word = "ABCCED"
输出：true
示例 2：

输入：board = [["a","b"],["c","d"]], word = "abcd"
输出：false
提示：

1 <= board.length <= 200
1 <= board[i].length <= 200

# 思路

# 关键点分析

# 代码

    var DFS = function(board, word, row, col, rows, cols, cur) {
        if(row >= rows || row < 0) return false;
        if(col >= cols || col < 0) return false;
        if(word[cur]!==board[row][col]) return false;
        board[row][col] = null;
        if(cur+1===word.length) return true;
        let res;
        res = DFS(board, word, row+1, col, rows, cols, cur+1)||
            DFS(board, word, row-1, col, rows, cols, cur+1)||
            DFS(board, word, row, col+1, rows, cols, cur+1)||
            DFS(board, word, row, col-1, rows, cols, cur+1);

        board[row][col]=word[cur];
        
        return res;
    }

    var exist = function(board, word) {
        if(word.length === 0) return true;
        if(board.length === 0) return false;
        let res = false;
        let rows = board.length, cols = board[0].length;
        for(let i = 0; i < board.length; i++) {
            for(let j = 0; j < board[0].length; j++) {
                res = DFS(board, word, i, j, rows, cols, 0);
                if(res) return true;
            }
        }
        return res;
    };
## [返回题目列表](../../README.md)