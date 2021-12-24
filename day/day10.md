### 思路

利用哈希 Set 先遍历存储 A 的节点，再遍历 B 寻找 Set 中是否有一样的节点，若有则返回这个节点，否则返回 null

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
 * @param {ListNode} headA
 * @param {ListNode} headB
 * @return {ListNode}
 */
var getIntersectionNode = function(headA, headB) {
    let set = new Set();
    let temp = headA;
    while(temp !== null) {
        set.add(temp);
        temp = temp.next;
    }
    temp = headB;
    while(temp !== null) {
        if(set.has(temp)) {
            return temp;
        }
        temp = temp.next;
    }
    return null;
};
```

**复杂度分析**

- 时间复杂度：O(M + N)，M，N 分别为两个链表的长度
- 空间复杂度：O(M)

