
### Mariadb CLI  

Command-line client for interacting with mariadb instance.  

`mariadb --user=user_name --password=password db_name`  

### Create Table  

```
CREATE [OR REPLACE] [TEMPORARY] TABLE [IF NOT EXISTS] tbl_name
    (create_definition,...) [table_options    ]... [partition_options]
CREATE [OR REPLACE] [TEMPORARY] TABLE [IF NOT EXISTS] tbl_name
    [(create_definition,...)] [table_options   ]... [partition_options]
    select_statement
CREATE [OR REPLACE] [TEMPORARY] TABLE [IF NOT EXISTS] tbl_name
   { LIKE old_table_name | (LIKE old_table_name) }


select_statement:
    [IGNORE | REPLACE] [AS] SELECT ...   (Some legal select statement)
```

*Note:* `SERIAL` data type is an alias for BIGINT UNSIGNED AUTO_INCREMENT NOT NULL
