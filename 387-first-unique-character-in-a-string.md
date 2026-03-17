# 387. First Unique Character in a String

- **問題 URL**: [https://leetcode.com/problems/first-unique-character-in-a-string/](https://leetcode.com/problems/first-unique-character-in-a-string/)
- **言語**: Python

写経元: https://github.com/hayashi-ay/leetcode/pull/28
各文字の出現回数を数えてから、先頭から順に出現回数 1 の文字を探す。(claude)

```python
from collections import defaultdict


class Solution:
    def firstUniqChar(self, s: str) -> int:
        freq = defaultdict(int)
        for c in s:
            freq[c] += 1
        for i, c in enumerate(s):
            if freq[c] == 1:
                return i
        return -1
```
