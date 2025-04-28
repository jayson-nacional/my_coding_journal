
# Arrays  

Arrays in PHP is an ordered map(type that associates values to keys). This can be optimized for different uses:  
- can be treated as an array
- list(vector)
- hash table(an implementation of map)
- dictionary
- collection
- stack
- queue  


## Syntax  

Can be created using the `array()` language construct. It takes any number of comma-separated key => value pairs as arguments.  

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

The key can only be either an `int` or a `string`. The value can be of any type.  


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

*Note*: Adding value to an array using the syntax `$arr[] = value` will result to adding an element to the last index of an array.  


## Array Behaviors  
- To remove a key/value pair inside an array, `unset()` method can be used
- When using the syntax `$array[] = value`, the index is automatically set to the largest existing `index + 1`
- Note that when using unset for the array elements, the value of indexes is retained. To reset the index back to 0 as the starting point use the `array_values($array)` function.  


## Array Destructuring  
```php
<?php
    $source_array = ["foo", "bar", "baz"];
    
    [$foo, $bar, $baz] = $source_array;

    echo $foo, PHP_EOL;     // prints "foo"
    echo $bar, PHP_EOL;     // prints "bar"
    echo $baz, PHP_EOL;     // prints "baz"
?>
```  

## Ignoring Elements on Destructure  

```php
<?php
    $source_array = ["foo", "bar", "baz"];
    
    [, , $baz] = $source_array;

    echo $baz, PHP_EOL;     // prints "baz"
?>
```

## Destructuring Associative Arrays  
```php
<?php
    $source_array = ["foo" => 1, "bar" => 2, "baz" => 3];

    ["baz" => $three] = $source_array;
    echo $three, PHP_EOL; // prints 3

    $source_array = ["foo", "bar", "baz"];

    [2 => $baz] = $source_array;
    echo $baz, PHP_EOL; // prints "baz"
?>
```  

## Using Destructuring technique to swap variable values  
```php
<?php
    $a = 1;
    $b = 2;

    [$a, $b] = [$b, $a];

    echo $a, PHP_EOL; // prints 2
    echo $b, PHP_EOL; // prints 1
?>
```  

*Note*: Always use qouted strings to access array index, otherwise it may be interpreted as a constant


## Converting to Array  

For any type of int, float, string, bool, and resource, converting a value to an array results in an array with a single element with index zero and the value of the scalar which was converted.

**Comparing Arrays** - possible with `array_diff()` function

**Array unpacking** - `[...$array]` (spread operator) => follows `array_merge()` behavior where later string keys overwrites earlier ones and integer keys are renumbered


## Changing element in the loop

```php
<?php
    $colors = array("red", "blue", "green", "yellow");

    foreach ($colors as &$color) {
        $color = mb_strtoupper($color);
    }

    unset($color); // ensures that following writes to $color will not overwrite the last array element
?>
```
