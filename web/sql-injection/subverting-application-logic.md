---
description: Change a query to interfere with the application's logic.
---

# Subverting application logic

Imagine a web app that has a login page. The user login with a username and password and the web app checks the credential by SQL query.

Of course, we won't be able to know the password. **What if** we remove the password check?

```sql
SELECT * FROM users WHERE username = 'administrator'--' AND password = ''
```
