### 思路

之前有见过，有想到用两个指针。但只想到了一半，第一次相遇的时候不一定在入环处，还需要重新改变快指针的指向，等第二次相遇才是入口处，看了题解。

### 代码

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var detectCycle = function(head) {
    let p = head, q = head;
    while(true) {
        if(q === null || q.next === null) return null;
        p = p.next;
        q = q.next.next;
        if(p == q) {
            break;
        }
    }
    q = head;
    while(p !== q) {
        p = p.next;
        q = q.next;
    }
    return q;
};
```

**复杂度分析**

- 时间复杂度：O(N)
- 空间复杂度：O(1)

