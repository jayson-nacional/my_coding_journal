
# Object Iteration  

It is possible to iterate through the properties of an object. See example below:  

```php
<?php
    class MyClass
    {
        public string $firstName = "John";
        public string $lastName = "Smith";
        public int $age = 25;

        public function iterateProperties()
        {
            foreach ($this as $key => $value) {
                echo "$key: $value", PHP_EOL;
            }
        }
    }

    $obj = new MyClass;
    $obj->iterateProperties();

    // Output
    // firstName: John
    // lastName: Smith
    // age: 25
?>
```
