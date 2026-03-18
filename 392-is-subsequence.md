# 392. Is Subsequence

- **問題 URL**: [https://leetcode.com/problems/is-subsequence/](https://leetcode.com/problems/is-subsequence/)
- **言語**: Python

コードはgeminiで生成しました。
2つのポインタで s と t を走査し、文字が一致したら s のポインタを進める。最後に s を全て走査できたか判定する。(claude)

```python
class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        s_index = 0
        t_index = 0
        while s_index < len(s) and t_index < len(t):
            if s[s_index] == t[t_index]:
                s_index += 1
            t_index += 1
        return s_index == len(s)
```