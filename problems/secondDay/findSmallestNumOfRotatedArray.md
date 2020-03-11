# 题目地址

[https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/](https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/)

# 题目描述
把一个数组最开始的若干个元素搬到数组的末尾，我们称之为数组的旋转。输入一个递增排序的数组的一个旋转，输出旋转数组的最小元素。例如，数组 [3,4,5,1,2] 为 [1,2,3,4,5] 的一个旋转，该数组的最小值为1。  

示例 1：

输入：[3,4,5,1,2]
输出：1
示例 2：

输入：[2,2,2,0,1]
输出：0

# 思路

# 关键点分析

# 代码

    var minArray = function(numbers) {
        let l = 0,r = numbers.length-1,m;
        while(l<r) {
            m = Math.floor((l+r)/2);
            //m = (l+r)>>1;  移位运算，可以在本题替代向下取整
            if(numbers[m] > numbers[r]) {
                l = m+1;
            } else if(numbers[m] < numbers[r]) {
                r = m;
            } else {
                r--;
            }
        }
        return numbers[l];
    };
## [返回题目列表](../../README.md)