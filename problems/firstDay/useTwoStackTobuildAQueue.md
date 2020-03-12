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
题目的输入是：第一个数组是操作序列，第二个数组尾部插入数字操作所需要的数字。

用两个栈实现一个队列的意思是：

假设有两数组i 和 j。

压栈的时候就在i中从0开始往后添加；出栈时对j操作，如果j不为空，则j执行出栈操作，否则对i按出栈顺序从后往前一个个清空i，将出栈的每一个数字按压栈顺序压入j中。

综上所述即实现了用两个栈表示一个队列的操作。

# 关键点分析

JS中，构造函数在构造可供对象实例使用的变量时，需用加上this，如下面的CQueue函数，在对象中使用时也需要用this引用相应的变量。

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