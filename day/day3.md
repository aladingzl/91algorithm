### 思路

用数组模拟一个栈，根据条件进行出栈跟入栈的操作，判断 k 与 length 的大小，对相应数量的元素进行增加 val 的操作

### 代码

```javascript
/**
 * @param {number} maxSize
 */
var CustomStack = function(maxSize) {
    this.stack = [];
    this.maxSize = maxSize;
};

/** 
 * @param {number} x
 * @return {void}
 */
CustomStack.prototype.push = function(x) {
    if(this.stack.length < this.maxSize) {
        this.stack.push(x);
    }
};

/**
 * @return {number}
 */
CustomStack.prototype.pop = function() {
    const ret = this.stack.pop();
    if(!ret) return -1;
    return ret; 
    
};

/** 
 * @param {number} k 
 * @param {number} val
 * @return {void}
 */
CustomStack.prototype.increment = function(k, val) {
    for(let i = 0; i < k && i < this.stack.length; i++) {
        this.stack[i] += val;
    }
};

/**
 * Your CustomStack object will be instantiated and called as such:
 * var obj = new CustomStack(maxSize)
 * obj.push(x)
 * var param_2 = obj.pop()
 * obj.increment(k,val)
 */
```

**复杂度分析**

- 时间复杂度：pop 和 push 操作 时间复杂度为 O(1) 增量操作的时间复杂度为 O(k)
- 空间复杂度：O(maxSize)

