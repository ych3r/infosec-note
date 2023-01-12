---
description: ''' or 1=1 -- -'
---

# 💉 SQL injection

## What is SQL injection?

In a common web application, people always use databases to store information. To interact with databases, people use SQL language. Hackers are trying to break those SQL queries, often by injecting something.

## What is the impact of it?

This is serious because databases are often used to store sensitive information, like passwords, credit card details, or social security numbers. Imagine hackers can CRUD (Create, Read, Update, Delete) them. Even more, in some cases, hackers can use SQL injection to compromise the server!

## How to exploit it?

{% content-ref url="sql-injection/retrieving-hidden-data.md" %}
[retrieving-hidden-data.md](sql-injection/retrieving-hidden-data.md)
{% endcontent-ref %}

{% content-ref url="sql-injection/subverting-application-logic.md" %}
[subverting-application-logic.md](sql-injection/subverting-application-logic.md)
{% endcontent-ref %}

{% content-ref url="sql-injection/union-attacks.md" %}
[union-attacks.md](sql-injection/union-attacks.md)
{% endcontent-ref %}

{% content-ref url="sql-injection/examining-the-database.md" %}
[examining-the-database.md](sql-injection/examining-the-database.md)
{% endcontent-ref %}

{% content-ref url="sql-injection/blind-sql-injection.md" %}
[blind-sql-injection.md](sql-injection/blind-sql-injection.md)
{% endcontent-ref %}

## How to detect it?



## How to prevent it?





ref:

* \[SQL injection]\([https://portswigger.net/web-security/sql-injection](https://portswigger.net/web-security/sql-injection))
* \[Testing for SQL Injection]\([https://github.com/OWASP/wstg/blob/master/document/4-Web\_Application\_Security\_Testing/07-Input\_Validation\_Testing/05-Testing\_for\_SQL\_Injection.md](https://github.com/OWASP/wstg/blob/master/document/4-Web\_Application\_Security\_Testing/07-Input\_Validation\_Testing/05-Testing\_for\_SQL\_Injection.md))
