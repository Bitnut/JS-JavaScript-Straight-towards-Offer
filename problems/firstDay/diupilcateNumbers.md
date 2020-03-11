# 题目地址

[https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)

# 题目描述

找出数组中重复的数字。


在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。

示例 1：

输入：
[2, 3, 1, 0, 2, 5, 3]
输出：2 或 3 
 

限制：

2 <= n <= 100000

# 思路

为了简化操作，可以在遍历数组的过程中利用一个 Map 存储已经出现的数字，以实现查找重复操作，遇到已经存在的数字即可返回。此方法时间复杂度和空间复杂度均为 O(N)O(N) 。



# 关键点分析

初次看到 Map 的同学不用慌，JS里面可以直接构造一个对象: var foo = {}，来实现 Map 的操作，关键在于将数组中元素下标与元素的映射改为————key(元素)与true(0/1也可)的映射。Map中的结构应该如下：
        {
            1: true;
            3: true;
            9: true;
        }
只有已经遍历过的数字会出现在 Map 中。

# 代码

    var findRepeatNumber = function(nums){
        var hash = {};
        for(var i=0; i<nums.length; i++){
            if(hash[nums[i]]){
                return nums[i];
            }
            else{
                hash[nums[i]] = true;
            }
        }
        return false;
    }