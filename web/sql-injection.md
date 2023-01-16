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

* Use single quote `'`and looking for errors.
* Use `SQL-specific syntax` and looking for systematic differences in responses.
* Use Boolean conditions like `OR 1=1` and `OR 1=2` and looking for differences in responses.
* Use `payload disigned to trigger time delays` and looking for differences in respond time.
* Use OAST payloads designed to trigger an out-of-band network interaction and monitoring for any resulting interactions.

## How to prevent it?

Use **Parameterized queries aka prepared statements** instead of string concatenation within the query.

From

```sql
String query = "SELECT * FROM products WHERE category = '"+ input + "'";
Statement statement = connection.createStatement();
ResultSet resultSet = statement.executeQuery(query);
```

To

```sql
PreparedStatement statement = connection.prepareStatement("SELECT * FROM products WHERE category = ?");
statement.setString(1, input);
ResultSet resultSet = statement.executeQuery();
```



ref:

* \[SQL injection]\([https://portswigger.net/web-security/sql-injection](https://portswigger.net/web-security/sql-injection))
* \[Testing for SQL Injection]\([https://github.com/OWASP/wstg/blob/master/document/4-Web\_Application\_Security\_Testing/07-Input\_Validation\_Testing/05-Testing\_for\_SQL\_Injection.md](https://github.com/OWASP/wstg/blob/master/document/4-Web\_Application\_Security\_Testing/07-Input\_Validation\_Testing/05-Testing\_for\_SQL\_Injection.md))
