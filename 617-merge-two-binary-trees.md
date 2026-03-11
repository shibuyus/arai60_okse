# 617. Merge Two Binary Trees

- **問題 URL**: [https://leetcode.com/problems/merge-two-binary-trees/](https://leetcode.com/problems/merge-two-binary-trees/)
- **言語**: Python
claudeでコードを生成しました。
再帰で解く。両方あれば値を足して左右を再帰、片方が None ならもう片方をサブツリーごと返す。(claude)

```python
class Solution:
    def mergeTrees(self, root1: Optional[TreeNode], root2: Optional[TreeNode]) -> Optional[TreeNode]:
        if not root1:
            return root2
        if not root2:
            return root1

        root1.val += root2.val
        root1.left = self.mergeTrees(root1.left, root2.left)
        root1.right = self.mergeTrees(root1.right, root2.right)

        return root1
```