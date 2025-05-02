
# Object Inheritance  

When overriding methods and properties from parent class, visibility modifiers can only be relaxed but cannot be restricted(i.e. `protected` to `public` is not valid)

*Note:* It is not allowed to override a read-write property with a readonly property or vice versa  

```php
<?php
    class A
    {
        public int $value;
    }

    class B extends A
    {
        public readonly int $value; // Illegal
    }
?>
```  

*Note:* When overriding a method, it is recommended to set the correct return type as PHP might emit deprecation notice if there is a mismatch on the method return types from parent to child classes.  


