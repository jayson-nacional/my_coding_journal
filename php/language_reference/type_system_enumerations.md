
# Enumerations  

Restricting layer on top of classes and constants, intended to provide a way to define a closed set of possible values for a type  

```php
<?php
    enum Suit 
    {
        case Hearts;
        case Diamonds;
        case Clubs;
        case Spades;
    }

    function do_stuff(Suit $s) {
    ...
    }
?>
```

When casting an object to an enum, value is retained. If array is casted, an array with single element with name key and enum value as the pair is generated.
