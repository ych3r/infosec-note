---
description: Extract information about the version and structure of the database.
---

# Examining the database

The version of Oracle DB:

```sql
SELECT * FROM v$version
```

Structure of the database:

```sql
SELECT * FROM information_schema.tables
```

more: [https://portswigger.net/web-security/sql-injection/examining-the-database](https://portswigger.net/web-security/sql-injection/examining-the-database)

cheat sheet: [https://portswigger.net/web-security/sql-injection/cheat-sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)
