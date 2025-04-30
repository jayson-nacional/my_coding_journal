
# Control Structures  

*Note:* Note that `elseif` and `else if` will only be considered exactly the same when using curly brackets as in the above example. When using a colon to define if/elseif conditions, the use of elseif in a single word becomes necessary. 

```php
<?php
    /* Correct Method */
    if ($a > $b):
        echo $a . " is greater than " . $b;
    elseif ($a == $b):
        echo $a . " equals " . $b;
    else:
        echo $a . " is neither greater than or equal to " . $b;
    endif;
?>
```  

## Control structures alternative syntax  

```php
<?php
    $i = 1;
    while ($i <= 10)
    {
        echo $i++;
    }
?>
```

... is identical to  

```php
<?php
    $i = 1;
    while ($i <= 10):
        echo $i++;
    endwhile;
?>
```


## Break  

`break` accepts an optional numeric argument, which tells it how many nested enclosing structures are to be broken out of. Default value is `1`  

```php
<?php
    $i = 0;
    while (++$i) {
        switch ($i) {
            case 5:
                echo "At 5";
                break 1;
            case 10:
                echo "At 10";
                break 2; // exits the switch and the while  
            default:
                break;
        }
    }
?>
``` 

## Continue  

`continue` accepts an optional numeric argument, which tells it how many nested enclosing structures are to be skip to the end of. Default value is `1`, thus skipping to the end of the current loop.  

```php
<?php
    $arr = ["zero", "one", "two", "three", "four", "five", "six"];
    foreach ($arr as $key => $value) {
        if (0 === ($key % 2)) { // skip members with even key
            continue;
        }
        
        echo $value, PHP_EOL;
    }
?>
```

It's possible to use a semicolon as an alternative to colon in switch statements cases  


## Match  

Unlike `switch`, the comparison is an identity check (===) rather than a weak equality check (==).  

**Using match expressions to handle non identity checks**  

```php
<?php
    $age = 23;
    
    $result = match ($age) {
        $age >= 65 => "senior",
        $age >= 25 => "adult",
        $age >= 18 => "young adult",
        default => kid
    };
?>
```

## Declare  

TODO: Need to learn about ticks

`require` is identical to `include` except that it also produce an `Error` exception whereas include only produce a warning.

## Include  

All functions and classes defined in the included file is treated as on a global scope  

TODO: further analysis on `require_once()` and `include_once()`
