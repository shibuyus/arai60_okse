# 3. Longest Substring Without Repeating Characters

- **問題 URL**: [https://leetcode.com/problems/longest-substring-without-repeating-characters/](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
- **言語**: Python

コードはclaudeで生成しました。
辞書で「文字 → 最後に出現した位置」を記録しながら、左右2つのポインタで窓をスライドさせる。右端を1つずつ進め、重複が見つかったら左端を前回の出現位置+1にジャンプさせる。

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        char_to_index = {}
        max_length = 0
        left = 0

        for right in range(len(s)):
            if s[right] in char_to_index and char_to_index[s[right]] >= left:
                left = char_to_index[s[right]] + 1
            char_to_index[s[right]] = right
            max_length = max(max_length, right - left + 1)

        return max_length
```
