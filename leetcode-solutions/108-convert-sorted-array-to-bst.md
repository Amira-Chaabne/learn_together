# 108. Convert Sorted Array to Binary Search Tree

Difficulty: Easy  
Link: [https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/)


```javascript
// -------- SOLUTION by @Youssef --------

// Date: 11-02-2026
// Language: Javscript
// Time: O(n)
// Space: O(log n) average – O(n) worst case (recursion stack)

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


```javascript
// -------- SOLUTION by @Amira --------

// Date: 11-02-2026
// one-liner xD
// Time: O(n)
// Space: O(log n)

var sortedArrayToBST = function(nums, start = 0, end = nums.length - 1) {
    if (start > end) return null;
    const mid = Math.floor((start + end) / 2);
    return new TreeNode(
        nums[mid],
        sortedArrayToBST(nums, start, mid - 1),
        sortedArrayToBST(nums, mid + 1, end)
    );
};
```
