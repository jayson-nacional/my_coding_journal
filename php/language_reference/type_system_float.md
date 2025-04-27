
# Float  

Also known as "floats", "doubles", or "real numbers"

```php
<?php
    $a = 1.234;
    $b = 1.2e3;
    $c = 7E-10;
    $d = 1_234.567; // as of PHP 7.4.0
?>
```  

Never trusts floating point numbers to the last digit due to floats limited precision. Do not compare equality betweeen floats.


## Converting to float  

- From strings, if the string/start of the string is numerical then it is converted to it's numerical counterpart, otherwise it is converted to 0
- For converting from other types, the value is initially converted to int, then from int it is converted to float.  


## Comparing floats  

Due to precision limitations of float, comparison between two floating point numbers is managed using a machine epsilon or unit roundoff, using the smallest acceptable difference

```php
<?php
    // test equality between $a and $b with 5 digits of precision
    $a = 1.23456789;
    $b = 1.23456780;
    $epsilon = 0.00001;

    if (abs($a - $b) < $epsilon) {
        echo "Values are equal";
    }
?>
```  

## NAN  

Cannot be compared to other values including itself, should be checked with `is_nan()`
