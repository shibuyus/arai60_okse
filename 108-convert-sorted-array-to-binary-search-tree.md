# 108. Convert Sorted Array to Binary Search Tree

- **問題 URL**: [https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/)
- **言語**: Python
claudeでコードを生成しました。
ソート済み配列の中央を根にし、左右の部分配列で再帰することでHeight-Balanced BSTを構築する。(claude)

```python
class Solution:
    def sortedArrayToBST(self, nums: List[int]) -> Optional[TreeNode]:
        if not nums:
            return None

        mid = len(nums) // 2
        root = TreeNode(nums[mid])
        root.left = self.sortedArrayToBST(nums[:mid])
        root.right = self.sortedArrayToBST(nums[mid + 1:])

        return root
```