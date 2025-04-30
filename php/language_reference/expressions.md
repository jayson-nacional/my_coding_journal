
# Expressions  

Anything that has a value. The most basic form are constants and variables.

PHP supports four scalar types (int, float, boolean, and string)

Expressions are evaluated from right to left. 
`$a = ($b = 5);` is the same as  
`$a = $b = 5;`

Pre-increment `++$expression;`
Post-increment `$expression++;`

Example of pre and post increment  

```php
<?php
    function double($i) {
        return $i * 2;
    }

    $b = $a = 5;
    $c = $a++; // $c here is still 5 while a becomes 6

    $e = $d = ++$b; // $b becomes 6 and assigning it to both $d and $e

    $f = double($d++); // the argument here is the original value of $d which is 6, so $f becomes 6 * 2, once execution has been completed then $d becomes 7  

    $g = double(++e); // $e here becomes 7 and is supplied as the argument value for double, therefore $g becomes 7 * 2

    $h = $g += 10; // the += operation is evaluated first making $g equal to 24 and assigns it to variable $h as well
?>
```
