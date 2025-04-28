
# Arrays  

Arrays in PHP is an ordered map(type that associates values to keys). This can be optimized for differen uses:  
- can be treated as an array
- list(vector)
- hash table(an implementation of map)
- dictionary
- collection
- stack
- queue  


## Syntax  

Can be created using the `array()` language construct. It takes any number of of comma-separated key => value pairs as arguments.  

```
array(
    key => value,
    key2 => value2,
    key3 => value3,
    ...
)
```

**Samples**  
```php
<?php
    $array1 = array(
        "foo" => "bar",
        "bar" => "foo",
    );

    // Using short array syntax
    $array2 = [
        "foo" => "bar",
        "bar" => "foo",
    ];
?>
```

The key can only be either an int or a string. The value can be of any type.  


As indexes can only be either a string or an int, use of keys which are of different type are automatically converted to int equivalent causing overwrites. See sample below:  
```php
<?php
    $array = array(
        1   => "a",
        "1" => "b",
        1.5 => "c",
        true => "d"
    );

    var_dump($array);
    
    // will result to
    // array(1) {
    //     [1] => string(1) "d"
    // }
?>
```

*Note:* Key is optional. If not specified, PHP will use the increment of the largest previously used `int` key.  

More samples:  
```php
<?php
    $array = array(
        1 => "a",
        "1" => "b", // the value "a" will be overwritten by value "b"
        1.5 => "c", // the value "b" will be overwritten by value "c"
        -1 => "d",
        "01" => "e", // as this is not an integer string, it will NOT override the key for 1
        "1.5" => "f", // as this is not an integer string, it will NOT override the key for 1
        true => "g", // the value "c" will be overwritten by "g"
        false => "h",
        "" => "i",
        null => "j", // the value "i" will be overwritten by "j"
        "k", // value  "k" is assigned the key 2. This is because the largest integer key before that was 1
        2 => "l", // the value "k" will be overwritten by "l"
    );

    var_dump($array);
?>php
```

## Accessing array elements with square bracket syntax  

```php
<?php
    $array = array(
        "foo" => "bar",
        42 => 24,
        "multi" => array(
            "dimensional" => array(
                "array" => "foo"
            )
        )
    );

    var_dump($array["foo"]);
    var_dump($array[42]);
    var_dump($array["multi"]["dimensional"]["array"]);
?>
```

    
