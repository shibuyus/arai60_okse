# 6. Zigzag Conversion

- **問題 URL**: [https://leetcode.com/problems/zigzag-conversion/](https://leetcode.com/problems/zigzag-conversion/)
- **言語**: Python

コードはclaudeで生成しました。
各行に対応するリストを用意し、行番号と方向（上/下）の2変数でジグザグの動きを追跡して文字を振り分ける。

```python
class Solution:
    def convert(self, s: str, numRows: int) -> str:
        if numRows == 1:
            return s

        rows = [[] for _ in range(numRows)]
        row_index = 0
        going_down = False

        for character in s:
            rows[row_index].append(character)
            if row_index == 0 or row_index == numRows - 1:
                going_down = not going_down
            if going_down:
                row_index += 1
            else:
                row_index -= 1

        return "".join("".join(row) for row in rows)
```
