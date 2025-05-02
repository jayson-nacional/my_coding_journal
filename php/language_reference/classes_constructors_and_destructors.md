
# Constructors and Destructors  

```php
<?php
    class BaseClass
    {
        function __construct ()
        {
            echo "Executed base class constructor.";
        }
    }

    class SubClass extends BaseClass
    {
        function __construct()
        {
            parent::__construct(); // call to the parent constructor
            echo "Executed the sub class constructor.";
        }
    }
?>
```

## Constructor Promotion  

```php
<?php
    class Point 
    {
        protected int $x;
        protected int $y;

        public function __construct(int $x, int $y = 0)
        {
            $this->x = $x;
            $this->y = $y;
        }
    }
?>
```  

Above can be expressed as  

```php
<?php
    class Point
    {
        public function __construct(protected int $x, protected int $y = 0) { }
    }
?>
```  


## New Initializers  

Instance of a class can be created using static functions that are following the same arguments as the constructors. See sample below:  

```php
<?php
    class MyClass
    {
        public function __construct(public string $name, public int $age) { }

        public static function fromStatic(string $name, int $age): static
        {
            $new = new static($name, $age);
            return new;
        }
    }

    $obj = MyClass::fromStatic("John Smith", 24);

    // $obj returns a new instance of MyClass
?>
```

Use `___destruct()` to create object destructors.  

TODO: Further research on descructors
