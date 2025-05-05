
# References  

Serves like aliases towards varibles. Does not work like pointers in C

Objects are passed as pointers and not reference  

## Passing by reference  

```php
<?php
    function foo(&$var)
    {
        $var++;
    }

    $a = 5;
    foo($a); // $a becomes 6
?>
```  

## Returning by reference  

```php
<?php
    class Foo
    {
        public $value = 42;

        public function &$getValue()
        {
            return $this->value;
        }
    }

    $obj = new Foo;
    $myValue = &$obj->getValue();
    $obj->value = 2;
    echo $myValue; // prints 2
?>
```

## Unsetting References  

```php
<?php
    $a = 1;
    $b =& $a;
    unset($a);
?>
```  

TODO: Learn more about references
