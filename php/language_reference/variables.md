
# Variables  

Only variables may be used as reference denoted by ampersand symbol(&)  

Array vivification automatically creates a variable, `$array[] = "test value"`  (phpactor detects this as an error but interpreter evaluates this as a valid declaration


## Predefined variables  

PHP variables that represent external values (i.e. $_SERVER, $_REQUEST, $_POST)


## Variable scope

```php
<?php
    $a = 1;
    $b = 2;

    function sum() {
        global $a, $b; // refers to variables $a and $b above/outside this function

        $b = $a + $b;
    }

    sum();
    echo $b;
?>
```  

Another way to access global variables is using the predefined variable `$GLOBALS`. (i.e. global variable $b can be accessed using `$GLOBALS["b"]`


## Static Variables  

Static variable inside a function doesn't lose its value after execution.  

Static variables inside anonymous functions are reinitialized each time the function is called.

Anonymous functions are declared using the syntax below
`$anonymous_func = (function () { ...statement here });`

If access to argument from parent function is required use the `use` keyword to supply the arguments, see below:
```php
<?php
    function parent_func($input) {
        $child_func = (function () use ($input) {
       });

        $child_func();
    }
?>
```


