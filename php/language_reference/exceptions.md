
# Exceptions  

PHP follows the same exception handling in other programming languages. `try` and `catch` block is also following the same syntax  

It is also possible to set a global exception handler via `set_exception_handler()` 

## Extending Exception

```php
<?php
    class CustomException extends Exception
    {
        public function __construct(string $message, int $code = 0, ?Throwable $previous = null)
        {
            parent::__construct($message, $code, $previous);
        }
    }
?>
```
