### 思路

判断终止的条件，利用递归分别比较左右子树，注意 不能写`if(p.val == q.val) return true;` 例如：[1,2] 跟 [1,null,2]

### 代码

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} p
 * @param {TreeNode} q
 * @return {boolean}
 */
var isSameTree = function(p, q) {
   if(p == null && q == null) return true;
   if(p == null || q == null) return false;
   if(p.val !== q.val) return false;
   return isSameTree(p.left, q.left) && isSameTree(p.right, q.right);
};
```

**复杂度分析**

- 时间复杂度：O(N)
- 空间复杂度：O(1)

