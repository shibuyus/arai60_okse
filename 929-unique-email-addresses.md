# 929. Unique Email Addresses

- **問題 URL**: [https://leetcode.com/problems/unique-email-addresses/](https://leetcode.com/problems/unique-email-addresses/)
- **言語**: Python

コードはclaudeで生成しました。
メールアドレスのlocal部を正規化（`+`以降を削除、`.`を削除）してsetで重複排除し、種類数を返す。

```python
class Solution:
    def numUniqueEmails(self, emails: list[str]) -> int:
        unique_emails = set()
        for email in emails:
            local, domain = email.split("@")
            local = local.split("+")[0]
            local = local.replace(".", "")
            unique_emails.add(f"{local}@{domain}")
        return len(unique_emails)
```