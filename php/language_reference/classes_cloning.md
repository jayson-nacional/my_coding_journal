
# Object Cloning  

When an object is cloned, PHP will perform a shallow copy of all the object's properties. Any properties that are references to other variables will remain references.  

TODO: Learn more about cloning behavior

```php
<?php
    class BaseClass
    {
        static int $instances;
        public $instance; // determine the order in the instances

        public function __construct()
        {
            $this->instances = ++self::$instances;
        }

        public function __clone()
        {
            $this->instance = ++self::$instances;
        }
    }

    class Cloneable
    {
        public $object1;
        public $object2;

        public function __clone()
        {
            $this->object1 = clone $object1;
        }
    }

    $obj1 = new Cloneable();
    $obj1->object1 = new BaseClass();
    $obj2->object2 = new BaseClass();

    $obj2 = clone $obj1; // this creates new copies of object1 and object2
?>
```
