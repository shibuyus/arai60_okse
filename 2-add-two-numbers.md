# 2. Add Two Numbers

- **問題 URL**: [https://leetcode.com/problems/add-two-numbers/](https://leetcode.com/problems/add-two-numbers/)
- **言語**: Python

コードはclaudeで生成しました。
2つの連結リストで表された数を筆算のように1桁ずつ足し、ダミーノードを使って結果の連結リストを構築する。

```python
class Solution:
    def addTwoNumbers(self, l1: ListNode | None, l2: ListNode | None) -> ListNode | None:
        dummy = ListNode()
        node = dummy
        carry = 0

        while l1 is not None or l2 is not None or carry:
            digit_sum = carry
            if l1 is not None:
                digit_sum += l1.val
                l1 = l1.next
            if l2 is not None:
                digit_sum += l2.val
                l2 = l2.next

            carry, digit = divmod(digit_sum, 10)
            node.next = ListNode(digit)
            node = node.next

        return dummy.next
```