# 111. Minimum Depth of Binary Tree

- **問題 URL**: [https://leetcode.com/problems/minimum-depth-of-binary-tree/](https://leetcode.com/problems/minimum-depth-of-binary-tree/)
- **言語**: Python

claudeでコードを生成しました。
再帰でルートからリーフまでの最短パスのノード数を求める。片方の子がNoneの場合はリーフではないため、もう片方の子の深さを返す。(claude)

```python
class Solution:
    def minDepth(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0

        if not root.left:
            return 1 + self.minDepth(root.right)
        if not root.right:
            return 1 + self.minDepth(root.left)

        return 1 + min(self.minDepth(root.left), self.minDepth(root.right))
```