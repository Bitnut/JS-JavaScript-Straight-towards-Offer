# 题目地址

[https://leetcode-cn.com/problems/bao-han-minhan-shu-de-zhan-lcof/](https://leetcode-cn.com/problems/bao-han-minhan-shu-de-zhan-lcof/)

# 题目描述
定义栈的数据结构，请在该类型中实现一个能够得到栈的最小元素的 min 函数在该栈中，调用 min、push 及 pop 的时间复杂度都是 O(1)。

 

示例:

MinStack minStack = new MinStack();
minStack.push(-2);
minStack.push(0);
minStack.push(-3);
minStack.min();   --> 返回 -3.
minStack.pop();
minStack.top();      --> 返回 0.
minStack.min();   --> 返回 -2.
 

提示：

各函数的调用总次数不超过 20000 次

# 思路

# 关键点分析

# 代码
    /**
    * initialize your data structure here.
    */
    var MinStack = function() {
        this.stack = [];
        this.minS = [];
    };

    /** 
    * @param {number} x
    * @return {void}
    */
    MinStack.prototype.push = function(x) {
        this.stack.push(x);
        if(this.minS.length === 0 || x <= this.minS[0]) {
            this.minS.unshift(x);
        }
    };

    /**
    * @return {void}
    */
    MinStack.prototype.pop = function() {
        let temp = this.stack.pop();
        if(temp === this.minS[0] && this.minS.length >= 1) {
            this.minS.shift();
        }
    };

    /**
    * @return {number}
    */
    MinStack.prototype.top = function() {
        return this.stack[this.stack.length-1];
    };

    /**
    * @return {number}
    */
    MinStack.prototype.min = function() {
        return this.minS[0];
    };

    /**
    * Your MinStack object will be instantiated and called as such:
    * var obj = new MinStack()
    * obj.push(x)
    * obj.pop()
    * var param_3 = obj.top()
    * var param_4 = obj.min()
    */
## [返回题目列表](../../README.md)