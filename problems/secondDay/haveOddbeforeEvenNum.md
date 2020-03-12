# 题目地址

[https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/](https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/)

# 题目描述
输入一个整数数组，实现一个函数来调整该数组中数字的顺序，使得所有奇数位于数组的前半部分，所有偶数位于数组的后半部分。

 

示例：

输入：nums = [1,2,3,4]
输出：[1,3,2,4] 
注：[3,1,2,4] 也是正确的答案之一。
 

提示：

1 <= nums.length <= 50000
1 <= nums[i] <= 10000

# 思路
二分法两头判断并遍历即可，循环跳出条件是head >= tail;
# 关键点分析

# 代码
    var exchange = function(nums) {
        let head = 0;
        let tail = nums.length-1;
        let temp = 0;
        while(head<tail){
            if(nums[head]%2) {
                if(nums[tail]%2) {
                    head++;
                } else {
                    head++;
                    tail--;
                }
            } else {
                if(nums[tail]%2) {
                    temp = nums[tail];
                    nums[tail] = nums[head];
                    nums[head] = temp;
                    tail--;
                    head++;
                } else {
                    tail--;
                }
            }
        }
        return nums;
    };
## [返回题目列表](../../README.md)