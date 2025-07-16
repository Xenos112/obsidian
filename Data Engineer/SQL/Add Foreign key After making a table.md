---
tags:
  - SQL
---
```sql
ALTER TABLE "Users"
ADD FOREIGN KEY(account_id) REFERENCES account.id
```