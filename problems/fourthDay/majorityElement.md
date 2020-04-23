# 题目地址

[https://leetcode-cn.com/problems/shu-zu-zhong-chu-xian-ci-shu-chao-guo-yi-ban-de-shu-zi-lcof/submissions/](https://leetcode-cn.com/problems/shu-zu-zhong-chu-xian-ci-shu-chao-guo-yi-ban-de-shu-zi-lcof/submissions/)

# 题目描述

数组中有一个数字出现的次数超过数组长度的一半，请找出这个数字。

 

你可以假设数组是非空的，并且给定的数组总是存在多数元素。

 

示例 1:

输入: [1, 2, 3, 2, 2, 2, 5, 4, 2]
输出: 2
 

限制：

1 <= 数组长度 <= 50000
# 思路

# 关键点分析

# 代码
JS:

    var majorityElement = function(nums) {
        nums.sort();
        re      turn nums[Math.floor((nums.length)/2)];
    };

C++:

class Solution {
    public:
        int majorityElement(vector<int>& nums) {
            sort(nums.begin(), nums.end());
            return nums[nums.size()/2];
        }
    };
## [返回题目列表](../../README.md)