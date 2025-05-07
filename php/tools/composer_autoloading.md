
# Autoloading  

Use the below config to define autoloading.  

```json
{
    "autoload": {
        "psr-4": {
            "MyPackage\\": "src/"
        }
    }
}
```

To use the autoloaded files, make sure to import the autoload file  

```php
<?php
    require __DIR__ . "/vendor/autoload.php";
?>
```  

To update the autoload file, use the `composer dump-autoload` command  

TODO: learn more about the `autoload` feature of composer. Also find more about optimizing autoloader
