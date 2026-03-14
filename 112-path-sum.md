# 112. Path Sum

- **問題 URL**: [https://leetcode.com/problems/path-sum/](https://leetcode.com/problems/path-sum/)
- **言語**: Python

claudeでコードを生成しました
再帰でルートからリーフまで進みながら targetSum から各ノードの値を引いていき、リーフで残りが0になれば True を返す。(claude)

```python
class Solution:
    def hasPathSum(self, root: Optional[TreeNode], targetSum: int) -> bool:
        if not root:
            return False

        if not root.left and not root.right:
            return targetSum == root.val

        return (self.hasPathSum(root.left, targetSum - root.val) or
                self.hasPathSum(root.right, targetSum - root.val))
```
でコードを生成しました