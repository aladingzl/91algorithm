### 思路

看到二叉树第一时间想到 DFS、BFS，想到归想到，就是不知道怎么去处理这个过程，本来想记录层数，来处理个十百千位，好像不太行，看了题解，可以这样

### 代码

```javascript
var sumNumbers = function(root) {
    const dfs = (root, preSum) => {
        if(root === null) return 0;
        const sum = preSum * 10 + root.val;
        if(root.left === null && root.right === null) {
            return sum;
        } else {
            return dfs(root.left, sum) + dfs(root.right, sum);
        }
    }
    return dfs(root, 0);
};
```

**复杂度分析**

- 时间复杂度：O(N)
- 空间复杂度：O(N)

