# 108. Convert Sorted Array to Binary Search Tree

**Difficulty**: Easy  
**Link**: [https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/)

## Solution Summary

| Aspect               | Value                                                |
| -------------------- | ---------------------------------------------------- |
| **Date**             | 2025-02-11                                           |
| **Language**         | Javscript                                            |
| **Time Complexity**  | O(n)                                                 |
| **Space Complexity** | O(log n) average – O(n) worst case (recursion stack) |

## Code

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
 * @param {number[]} nums
 * @return {TreeNode}
 */
var sortedArrayToBST = function (nums) {
  if (!nums.length || nums.length === 0) return null;
  const center = Math.floor(nums.length / 2);
  const tree = new TreeNode(nums[center]);
  tree.left = sortedArrayToBST(nums.slice(0, center));
  tree.right = sortedArrayToBST(nums.slice(center + 1));
  return tree;
};
```
