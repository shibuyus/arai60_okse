# 349. Intersection of Two Arrays
- **問題URL**: [https://leetcode.com/problems/intersection-of-two-arrays/](https://leetcode.com/problems/intersection-of-two-arrays/)
- **言語**: Python

コードはgeminiで生成しました。
setはハッシュテーブルで実装されている。値のハッシュ値からスロット位置を算出して格納する。同じ値を追加しようとすると、ハッシュ値と__eq__が一致するため格納がスキップされる。(claude)

```python
class Solution:
    def intersection(self, nums1: List[int], nums2: List[int]) -> List[int]:
        set1 = set(nums1)
        set2 = set(nums2)
        res = set1 & set2

        return list(res)
```
