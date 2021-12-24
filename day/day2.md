### 思路

从低位开始，将 A 的每一位与 K 的每一位相加，和大于10时，记录进位 “+1”，将和放到数组中，考虑 K 的长度大于 A 的情况，最后将数组翻转，返回结果

### 代码

```javascript
/**
 * @param {number[]} num
 * @param {number} k
 * @return {number[]}
 */
var addToArrayForm = function(num, k) {
   const res = [];
   for(let i = num.length - 1; i >= 0; i--) {
       let sum = num[i] + k % 10;
       k = Math.floor(k / 10);
       if(sum >= 10) {
           k++;
           sum -= 10;
       } 
       res.push(sum);
   }
   for(; k > 0; k = Math.floor(k / 10)) {
       res.push(k % 10);
   }
   res.reverse();
   return res;
};
```

**复杂度分析**

- 时间复杂度：O(N)
- 空间复杂度：O(N)

