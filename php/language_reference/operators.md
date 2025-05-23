

# Operators  

Unary operators - takes only one value. Includes logical `not` (!) operator and increment operators. Binary operator takes two values and ternary operator (? :) takes three values  


## Operator Precedence  

(*) and (/) operators takes precedence on (+) and (-) operators  

(+, -, *, /) operators are left-associative (meaning they are normally evaluated left to right), while = operator is right-associative as it is evaluated from right to left  

Operators of equal precedence and non-associative cannot be used next to each other (i.e. `1 < 2 > 3`)

The expression `1 <= 1 == 1` is legal as the `==` operator takes lower precedence than `<=`  

TODO: Learn more about the order or precedence of operators and its practical use case  


## Arithmetic  


| Operator | Name | Description |
| --- | --- | --- |
| +$a | Identity Operator | Conversion of $a to `int` or `float` as appropriate  |
| -$a | Negation  | Opposite of $a|
| $a + $b | Addition  | Sum of $a and $b|
| $a - $b | Subtraction | Difference of $a and $b|
| $a * $b | Multiplication    | Product of $a and $b|
| $a / $b | Division  | Quotient of $a and $b|
| $a % $b | Modulo    | Remainder of $a divided by $b|
| $a ** $b    | Exponentiation    | Result of $a raising to the $b'th power  |

For modulo operator, the sign of the the left hand value is used  

## Assignment  

PHP follows assignment by value. Objects and arrays are assigned by reference  


TODO: Learn about bitwise operators


## Comparison  

| Operator  |   Name    |
|   --- |   --- |
|   $a == $b    |   Equal   |
|   $a ==== $b  |   Identical   |
|   $a != $b    |   Not Equal   |
|   $a <> $b    |   Not Equal   |
|   $a !== $b   |   Not Identical   |
|   $a < $b |   Less Than   |
|   $a > $b |   Greater Than    |
|   $a <= $b    |   Less Than or Equal  |
|   $a >= $b    |   Greater Than or Equal   |
|   $a <=> $b   |   Spaceship   |


*Note:* You should not compare floating point numbers using normal comparison operators due to its behavior. Use epsilon to compare it to the difference of two floating numbers.

## Ternary Operator  
```php
<?php
    if (empty($_POST["action"])) {
        $action = "default";
    } else {
        $action = $_POST["action"];
    }

    // above can be expressed as 
    $action = empty($_POST["action"]) ? "default" : $_POST["action"];
?>
```

## Null Coalescing Operator  

Use `??` to perform null coalescing
```php
<?php
    if (isset($_POST["action"])) {
        $action = $_POST["action"];
    } else {
        $action = "default";
    }

    // above can be expressed as
    $action = $_POST["action"] ?? "default";
?>
```

Null Coalescing has lower precedence with operators like string concatenation, so parenthesis is required.
```php
<?php
    echo "Hello Mr. " . $name ?? "Anonymous"; // incorrect
    
    echo "Hello Mr. " . ($name ?? "Anonymous"); // correct
?>
```

## Error Control Operators  

PHP supports the error control operator: the at sign(@)

When prepended to an expression in PHP, any diagnostic error that might be generated by that expression will be suppressed.

If a custom error handler function is set with `set_error_handler()`, it will still be called even though the diagnostic has been suppressed.

Use `error_get_last()` function to get the message generated by previous error
```php
<?php
    // Intentional file error
    $my_file = @file("non_existent_file") or
        die ("Failed opening file: error was '" . error_get_last()["message"] . "'");

    $value = @cache[$key]; // will not issue a notice if $key doesn't exist
?>
```

## Execution Operators  

PHP uses backticks (``) to denote shell operation. Output can be saved to a variable. Identical to `shell_exec()` function  
```php
<?php
    $output = `ls -al`
    echo "<pre>$output</pre>";
?>
```

## Logical Operators  

|   Example |   Name    |   Result  |
|   --- |   --- |   --- |
| $a and $b | And | true if both $a and $b are true |
| $a or $b | Or | true if either $a or $b are true |
| $a xor $b | Xor | true if either $a or $b are true, but not both |
| !$a | Not | true if $a is not true |
| $a && $b | And | true if both $a and $b are true |
| $a \|\| $b | Or | true if either $a or $b are true |

*Note:* || has greater precedence than `or`  


## String Operators  

Use dot(.) for concatenation. Another option is the concatenating assignment operator(.=)  


## Array Operators  

| Example | Name | Result |
| --- | --- | --- |
| $a + $b | Union | Union of $a and $b |
| $a == $b | Equality | true if $a and $b have the same key/value pairs |
| $a === $b | Identity | true if $a and $b have the same key/value pairs in the same order and of the same types |
| $a != $b | Inequality | true if $a is not equal to $b |
| $a <> $b | Inequality | true if $a is not equal to $b |
| $a !== $b | Non-identity | true if $a is not identical to $b |  


## Type Operators  

`instanceof` is used to determine whether a variable is an instantiated object of certain class. This can also be used to determine whether a variable is an instantiated object of a class that inherits from a parent class. Lastly, it can also be used to determine whether a variable is an instantiated object of a class that impelements an interface.  


