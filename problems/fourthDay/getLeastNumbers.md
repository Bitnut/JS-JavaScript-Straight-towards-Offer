# 题目地址

[https://leetcode-cn.com/problems/zui-xiao-de-kge-shu-lcof/submissions/](https://leetcode-cn.com/problems/zui-xiao-de-kge-shu-lcof/submissions/)

# 题目描述
输入整数数组 arr ，找出其中最小的 k 个数。例如，输入4、5、1、6、2、7、3、8这8个数字，则最小的4个数字是1、2、3、4。

 

示例 1：

输入：arr = [3,2,1], k = 2
输出：[1,2] 或者 [2,1]
示例 2：

输入：arr = [0,1,2,1], k = 1
输出：[0]
 

限制：

0 <= k <= arr.length <= 10000
0 <= arr[i] <= 10000

# 思路

# 关键点分析
JS 一定要注意，sort 方法是按照数字的字符串顺序排序的！排序的时候注意传一个比较函数。
# 代码
JS:

var getLeastNumbers = function(arr, k) {
    arr.sort((a, b) => a - b);
    return arr.slice(0, k);
};

C++:

    class Solution {
    public:
        vector<int> getLeastNumbers(vector<int>& arr, int k) {
            if(k == 0) return vector<int>();
            sort(arr.begin(), arr.end());
            return vector<int>(arr.begin(), arr.begin()+k);
        }
    };
## [返回题目列表](../../README.md)