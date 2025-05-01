
# Functions  

## User-defined Functions  

**Conditional Functions**  
```php
<?php
    $makefoo = true;

    if ($makefoo) {
        function foo () {
            echo "Foo function doesn't exists until program execution reaches here";
        }
    }
?>
```  

**Functions within functions**
```php
<?php
    function foo () {
        function bar () {
            echo "This function doesn't exist until foo () is called";
        }
    }

    foo();
    
    // now we can call the bar () function
    bar();
?>
``` 

## Passing by reference  

```php
<?php
    function append_some_text(&$str)
    {
        $str .= ", has been added with next text";
    }

    $str = "hello, world!";
    append_some_text($str);

    echo $str; // hello, world!, has been added with next text 
?>
```  

## Using default parameters  

```php
<?php
    function pick_color($color = "blue")
    {
        echo "You have chosen $color", PHP_EOL;
    }

    pick_color(); // You have chosen blue
    pick_color("white"); // You have chosen white
?>
```  

Default value must be a constant expression, cannot be a variable, class member or a function  

It's possible to call a function with named parameters (i.e. `pick_color(color: "magenta")`)


## Variable-length argument lists  

Spread operator can be used to let functions accept variable number of arguments  

```php
<?php
    function sum(...$numbers)
    {
        $sum = 0;
        foreach ($numbers as $number) {
            $sum += $number;
        }

        return $sum;
    }

    echo sum(1, 2, 3, 4); // prints 10
?>
```  

## Using spread operator to provide arguments  

```php
<?php
    function add($a, $b) {
        return $a + $b;
    }

    echo add(...[1, 2]) . PHP_EOL;

    $a = [1, 2];
    echo add(...$a) . PHP_EOL;
?>
```

## Returns  

```php
<?php
    function &return_reference()
    {
        return $someref;
    }

    $newref =& return_reference();
?>
```  


## Variable functions  

```php
<?php
    function foo()
    {
        echo "foo() has been executed" . PHP_EOL;
    }

    $func = 'foo';
    $func(); // this calls foo()
?>
```  

## Complex callables  

```php
<?php
    class Foo
    {
        static function bar()
        {
            echo "bar" . PHP_EOL;
        }

        function baz()
        {
            echo "baz" . PHP_EOL;
        }
    }

    $func = array("Foo", "bar");
    $func(); // prints bar

    $func = array(new Foo, "baz");
    $func(); // prints baz

    $func = "Foo::bar";
    $func(); // prints bar
?>
```

## Anonymous Functions  

Also known as `closures`

```php
<?php
    $greet = function($name) {
        echo "Hello, $name", PHP_EOL;
    };
    
    $greet("World!"); // Hello, World!
?>
```

**Inheriting variables from parent scope**  
```php
<?php
    $message = "hello";

    // Basic - no use
    $func = function () {
        var_dump($message);
    };
    $func();

    // Inherit $message
    $func = function () use ($message) {
        var_dump($message);
    };
    $func();

    // Inherited variable's value is from when the function is defined, not when called
    $message = "world";
    $func(); // will still output 'hello'

    // Inherit by reference
    $example = function () use (&$message) {
        $message = "updated";
    };
    $example();
    var_dum($message); // output is 'updated'

    // Can also pass regular arguments
    $func_args = function ($args) use ($message) {
        var_dump($args);
        var_dump($message);
    };
?>
```  

TODO: Study how `array_walk()`, `bindTo()` works  

## Arrow functions  

More concise syntax for anonymous functions  

```php
<?php
    $test = fn ($x, $y) => $x + $y;
    var_dump($test(1, 2)); // int (3)

    // equivalent to  
    $another_test = function ($x, $y) {
        return $x + $y;
    }
    var_dump($another_test(1, 3)); // int(4)
?>
```

**Nested arrow functions**  

```php
<?php
    $z = 1;
    $fn = fn ($x) => fn ($y) => $x * $y + $z;

    var_dump($fn(5)(10)); // int (51)
?>
```  

## First class callable syntax  

TODO: need to further understand how this works 

    

    
    
