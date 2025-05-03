
# Class Abstraction  

Creates a template for the child classes. No new object instance can be created from abstract classes  

```php
<?php
    abstract class AbstractClass
    {
        abstract protected function getValue();
        abstract protected function formatValue($value);
    }
?>
```

TODO: do further research on the best way to use abstraction
