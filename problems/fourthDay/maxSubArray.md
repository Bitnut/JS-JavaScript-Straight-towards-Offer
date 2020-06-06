# 题目地址

[https://leetcode-cn.com/problems/lian-xu-zi-shu-zu-de-zui-da-he-lcof/](https://leetcode-cn.com/problems/lian-xu-zi-shu-zu-de-zui-da-he-lcof/)

# 题目描述
输入一个整型数组，数组里有正数也有负数。数组中的一个或连续多个整数组成一个子数组。求所有子数组的和的最大值。

要求时间复杂度为O(n)。

 

示例1:

输入: nums = [-2,1,-3,4,-1,2,1,-5,4]
输出: 6
解释: 连续子数组 [4,-1,2,1] 的和最大，为 6。
 

提示：

1 <= arr.length <= 10^5
-100 <= arr[i] <= 100

# 思路

# 关键点分析

# 代码
C++:
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
      if(nums.size() == 1) {
	return nums[0];
      }
      int max_val = nums[0];
      for(int i = 1; i < nums.size(); ++i) {
	nums[i] += max(0, nums[i-1]);
	max_val = max(max_val, nums[i]);
      }
      return max;
    }
  int max(int i, int j) {
    return i>j?i:j;
  }
};

JS：
var maxSubArray = function(nums) {
    if(nums.length === 1) {
	return nums[0];
    }
    let max = function(i, j) {
	return i>j ? i : j;
    };
    let max_val = nums[0];
    for(let i = 1; i < nums.length; ++i) {
	nums[i] += max(0, nums[i-1]);
	max_val = max(max_val, nums[i]);
    }
    return max_val;
};

## [返回题目列表](../../README.md)
