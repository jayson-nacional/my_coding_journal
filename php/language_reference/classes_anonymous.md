
# Anonymous Classes  

They can pass arguments through to their constructors, extend other classes, implement interfaces and use traits just like normal classes can  

```php
<?php
    class SomeClass { }
    interface SomeInterface { }
    trait SomeTrait { } 

    var_dump(new class(10) extends SomeClass impelements SomeInterface
    {
        private $num;

        public function __construct($num)
        {
            $this->num = $num;
        }

        use SomeTrait;
    });
?>
```

All objects created by the same anonymous class declaration are instances of that very class

Readonly identifier can be applied to anonymous classes
