
# Magic Methods  

Are special methods which overrides PHP's default action when certain actions are performed on an object  

Below are considered the list of magic methods:  
- __construct()
- __destruct()
- __call()
- __callStatic
- __get()
- __set()
- __isset()
- __unset()
- __sleep()
- __wakeup()
- __serialize()
- __unserialize()
- __toString()
- __invoke()
- __set_state()
- __clone()
- __debuginfo()

`serialize()` checks if the class has a magic method `__sleep()` as it is executed before any serialization happens. Serialize returns null if no sleep is available and E_NOTICE is released.  

TODO: needs further understanding on the behavior of sleep and wakeup (i.e. for database connections)

When `serialize()` method is called against an object, the `__serialize()` magic method is invoked

`__toString()` implements on how the string conversion for a class will be facilitated. Given an object of class `ClassA`, when using the object as string (i.e. on `echo $obj`) then the `__toString()` implementation will be called. This returns a `string`  

`__invoke()` is called when an object is used like a function  

```php
<?php
    class MyClass
    {
        public function __invoke(mixed $args)
        {
            echo "invoke magic method has been called...", PHP_EOL;
            var_dump($args);
        }
    }

    $obj = new MyClass;
    $obj(100); // will trigger the __invoke method
?>
```  

`__set_state()` - is called for classes exported by `var_export()`  


`__debugInfo()` - is called when `var_dump()` is executed against an object
