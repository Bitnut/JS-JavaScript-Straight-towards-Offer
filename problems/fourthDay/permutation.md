# 题目地址

[https://leetcode-cn.com/problems/zi-fu-chuan-de-pai-lie-lcof/submissions/](https://leetcode-cn.com/problems/zi-fu-chuan-de-pai-lie-lcof/submissions/)

# 题目描述
输入一个字符串，打印出该字符串中字符的所有排列。

 

你可以以任意顺序返回这个字符串数组，但里面不能有重复元素。

 

示例:

输入：s = "abc"
输出：["abc","acb","bac","bca","cab","cba"]

# 思路
对字符串用 dfs 作回溯
# 关键点分析
js需要注意字符串的字符swap是不正确的，需要通过折中的方法处理
# 代码
JS

var permutation = function(s) {
    let res = [];
    var judge = function(str, pos, i) {
        for(let k = pos; k < i; k++) {
            if( str[k] === str[i]) return true;
        }
        return false;
    }
    var dfs = function(str, pos) {
        if(pos === s.length) {
            res.push(str.join(''));
            return;
        }
        for( let i = pos; i < s.length; i++) {
            if(judge(str, pos, i)) continue;
            [str[pos], str[i]] = [str[i], str[pos]];
            dfs(str, pos + 1);
            [str[pos], str[i]] = [str[i], str[pos]];
        }
    }
    dfs(s.split(''), 0);
    return res;
};

C++

    class Solution {
    public:
        vector<string> permutation(string s) {
            vector<string> res;
            dfs(res, 0, s);
            return res;
        }
        void dfs(vector<string> &res, int pos, string &s) {
            if(pos == s.size()) {
                res.push_back(s);
                return;
            }
            for(int i = pos; i < s.size(); i++) {
                if(judge(s, pos, i)) continue;
                swap(s[pos], s[i]);
                dfs(res, pos + 1, s);
                swap(s[pos], s[i]);
            }
        }
        bool judge(string s, int pos, int i) {
            for(int k = pos; k < i; k++) {
                if(s[k] == s[i]) {
                    return true;
                }
            }
            return false;
        }
    };
## [返回题目列表](../../README.md)