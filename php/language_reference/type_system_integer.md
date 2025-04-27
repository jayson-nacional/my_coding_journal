
# Integers  

An integer is a number of the set Z = {..., -2, -1, 0, 1, 2, ...}  

Ints doesn't support unsigned values. Ints can be specified in decimal(base 10), hexadecimal(base 16), octal(base 8) or binary(base 2)  

```php
<?php
    $a = 1234; // decimal number
    $a = 0123; // octal number (equivalent to 83 decimal)
    $a = 0o123; // octal number (as of PHP 8.1.0)
    $a = 0x1A; // hexadecimal number (equivalent to 26 decimal)
    $a = 0b11111111; // binary number (equivalent to to 255 decimal)
    $a = 1_234_567; // decimal number (as of PHP 7.4.0)
?>
```  

**Integer Overflow**  

Integer size is platform independent. Size, Min and Max values are identified using PHP_INT_SIZE, PHP_INT_MAX, PHP_INT_MIN  
If PHP encounters an int beyond the bounds of int type, it is automatically interpreted as float type. Operations that results in number beyond bounds of int are returned as float.  

```php
<?php
    var_dump(PHP_INT_MAX + 1); // returns float
?>
```  

**Integer Division**
- Casting (int) to a float will round the value to zero
- Use `round()` function to have finer control over rounding

**Converting to Integer**
- If (int) is casted on a `resource` value then it will return the unique resource number during PHP runtime
- Boolean false will be converted to 0 and true to 1
- When casting (int) to a float, the value will be rounded towards zero
- If casting (int) to a float that is beyond bounds of the int type, the result will be undefined
- `NaN`, `Inf`, and `-Inf` returns 0 when cast as int
- For `strings`, when the value is numerical or leading with numbers it is converted to the numerical equivalent, otherwise will return 0
- `NULL` is always converted to 0

