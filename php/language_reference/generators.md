
# Generators  

Provides a way to make a result iterable rather than creating a class that implements the `Iterator` interface. 

```php
<?php
    function sample_generator(int $start, int $end)
    {
        for ($i = $start; $i <= $end; $i++)
        {
            yield $i; // this creates an output based on current iteration, without creating an entire array (beneficial for saving memory)
        }
    }

    foreach (sample_generator(1, 5) as $item)
    {
        echo $item . " ";
    }
    
    // output 1 2 3 4 5
?>
```  

## Generator Syntax  

Works like a function but instead of using `return` it utilizes `yield` syntax

To yield values with keys `yield $key => $value;`

To yield `null` values use the syntax `yield;`  

**Yield by reference**  

```php
<?php
    function &yield_by_reference()
    {
        int $i = 0;
        while ($i <= 5)
        {
            yield $i;
        }
    }

    // To use
    foreach (yield_by_reference() as &$item)
    {
        ...
    }
?>
```

**Generator Delegation via Yield from**  

```php
<?php
    function custom_gen()
    {
        yield 1;
        yield 2;
        yield 3;
    }

    function new_gen()
    {
        yield 4;
        yield 5;
        yield from custom_gen();
    }
?>
```

TODO: Learn all about iterators and how it's built
