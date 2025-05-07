
# MySQL PDO  

Lightweight, consistent interface for accessing MySQL database in PHP  

## Connecting to database  

```php
<?php
    use PDO;

    $username = "my_user";
    $password = "my_password";

    $db = new PDO("mysql:host=localhost;dbname=test_db;", $username, $password);

    // Optionally connectivity can be tested and retried using a try catch block
    
    try {
        $db2 = new PDO("mysql:host=localhost;dbname=test_db;", $username, $password);
    } catch (Exception $e) {
        echo "Error connecting to database.", PHP_EOL;
        
        // can perform retry here
    }
?>
```  

## Using Transactions and Auto-commit  

In some occassions, it is optimal to perform several requests/queries and commit it as a transaction in one go. PDO allows this using `beginTransaction()` and `commit()` methods.

```php
<?php
    $pdo->beginTransaction();
    $pdo->exec("valid sql statement here...");
    $pdo->exec("another valid sql statement here...");
    $pdo->exec("another valid sql statement here...");
    $pdo->commit();
?>
```  

PDO also allows rollback for transactions (i.e. if error happened during processing of transaction)  

```php
<?php
    try {
        $pdo->beginTransaction();
        $pdo->exec("valid sql statement here...");
        $pdo->exec("another valid sql statement here...");
        $pdo->exec("another valid sql statement here...");
        $pdo->commit();
    } catch (Exception $e) {
        echo "Performing rollback.", PHP_EOL;
        $pdo->rollBack();
    }
?>
```  

## Prepared Statements  

Substitution by named parameter  

```php
<?php
    $stmt = $pdo->prepare("INSERT  INTO test_table(col1, col2) VALUES(:col1, :col2));
    $stmt->bindParam(":col1", $col1);
    $stmt->bindParam(":col2", $col2);

    $col1 = "test1";
    $col2 = "test2";
    $stmt->execute(); // will insert a row

    $col1 = "test3";
    $col2 = "test4";
    $stmt->execute(); // will insert another row
?>
```

Using position `?` parameter  

```php
<?php
    $stmt = $pdo->prepare("INSERT  INTO test_table(col1, col2) VALUES(?, ?));
    $stmt->bindParam(1, $col1);
    $stmt->bindParam(2, $col2);

    $col1 = "test1";
    $col2 = "test2";
    $stmt->execute(); // will insert a row

    $col1 = "test3";
    $col2 = "test4";
    $stmt->execute(); // will insert another row
?>
```  

The type of bounded parameter can also be defined using the syntax  
`$stmt->bindParam(":param", $value, PDO::PARAM_STR)`

