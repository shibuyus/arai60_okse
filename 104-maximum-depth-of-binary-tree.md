# 104. Maximum Depth of Binary Tree

- **問題 URL**: [https://leetcode.com/problems/maximum-depth-of-binary-tree/](https://leetcode.com/problems/maximum-depth-of-binary-tree/)
- **言語**: Python

コードは claude で生成しました。
再帰（DFS）で解く。各ノードが「左右の子の深い方 + 自分の 1」を返す。None にたどり着いたら 0 を返して、+1 が積み上がって最終的な深さになる。(claude)

```python
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0

        left = self.maxDepth(root.left)
        right = self.maxDepth(root.right)

        return max(left, right) + 1
```
