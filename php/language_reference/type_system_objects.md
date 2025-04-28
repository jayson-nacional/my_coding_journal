
# Objects  

To create a new object use the new statement to instantiate a class.


## Converting to object  

```php
<?php
    $obj = (object) array("1" => "foo");
    var_dump(isset($obj->{"1"})); // outputs bool(true)
?>
```  

```php
<?php
    $obj = (object) "ciao";
    echo $obj->scalar; // outputs "ciao"
?>
```
