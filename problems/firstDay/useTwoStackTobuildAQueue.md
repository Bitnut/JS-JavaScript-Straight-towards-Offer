# 题目地址

[https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/](https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/)

# 题目描述
用两个栈实现一个队列。队列的声明如下，请实现它的两个函数 appendTail 和 deleteHead ，分别完成在队列尾部插入整数和在队列头部删除整数的功能。(若队列中没有元素，deleteHead 操作返回 -1 )


示例 1：

输入：
["CQueue","appendTail","deleteHead","deleteHead"]
[[],[3],[],[]]
输出：[null,null,3,-1]
示例 2：

输入：
["CQueue","deleteHead","appendTail","appendTail","deleteHead","deleteHead"]
[[],[],[5],[2],[],[]]
输出：[null,-1,null,null,5,2]

# 思路

# 关键点分析

# 代码

    var CQueue = function() {
        this.instack = [];
        this.outstack = [];
    };

    /** 
    * @param {number} value
    * @return {void}
    */
    CQueue.prototype.appendTail = function(value) {
        this.instack.push(value);
    };

    /**
    * @return {number}
    */
    CQueue.prototype.deleteHead = function() {
        const {outstack, instack} =  this;
        if(outstack.length) {
            return outstack.pop();
        } else {
            while(instack.length){
                outstack.push(instack.pop());
            }
            return outstack.pop()||-1;
        }
    };

    /**
    * Your CQueue object will be instantiated and called as such:
    * var obj = new CQueue()
    * obj.appendTail(value)
    * var param_2 = obj.deleteHead()
    */

## [返回题目列表](../../README.md)