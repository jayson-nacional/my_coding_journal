
# Autoloading classes  

**Autoload by autoload register**  

```php
<?php
    spl_autoload_register(function ($class_name) {
        include $class_name . ".php";
    });
?>
```  

**Autoloading using composer**  

```php
<?php
    require __DIR__ . "/vendor/autoload.php";
?>
```  

TODO: further research on autoloading with `composer`
