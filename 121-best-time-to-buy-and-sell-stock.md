# 121. Best Time to Buy and Sell Stock

- **問題 URL**: [https://leetcode.com/problems/best-time-to-buy-and-sell-stock/](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)
- **言語**: Python

claudeでコードを生成しました
配列を左から走査しながら「今までの最安値」を保持し、各日で「今日売ったら利益いくらか」を計算して最大値を更新する。Greedyパターン。(claude)

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        min_price = float('inf')
        max_profit = 0
        for price in prices:
            max_profit = max(max_profit, price - min_price)
            if price < min_price:
                min_price = price
        return max_profit
```