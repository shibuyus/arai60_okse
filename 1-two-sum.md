# 1. Two Sum

- **問題 URL**: [https://leetcode.com/problems/two-sum/](https://leetcode.com/problems/two-sum/)
- **言語**: Python
ハッシュマップで既出の数値とインデックスを記録しながら、補数が存在するか確認する。(claude)
写経元: https://github.com/hayashi-ay/leetcode/pull/14
まだ右も左も分からないため、完走者の方のコードを写経させていただきました。

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_to_index = {}
        for i, num in enumerate(nums):
            complement = target - num
            if complement in num_to_index:
                return [num_to_index[complement], i]
            num_to_index[num] = i
        raise Exception("unreachable")
```
