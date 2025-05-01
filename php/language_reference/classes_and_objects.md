
# Classes and Objects  

Classes may contain constants (properties) and functions (methods)  

## Readonly Classes  

When class is declared as `readonly`, having dynamic properties becomes impossible. It can only be extended if and only if the child class is also readonly  

Classes can be declared using expressions that returns a string - has a corresponding class name  

Class instances are passed as reference. Instances copy can be created by `cloning`.

Classes can be declared through a variable that contains an instance of an object  
```php
<?php
    class Person { }

    $obj = new Person;
    $obj2 = new $obj;
?>
```  

It's possible to declare a class property and method with the same name as those are having different namespaces  
```php
<?php
    class MyClass
    {
        public string $test = "test";

        public function test() { }
    }

    $obj = new MyClass;
    $obj->test; // treated a access to class property
    $obj->test(); // call to the class method test
?>
```  

## Assigning an anonymous function to a property  

Calling an anonymous function assigned to a property cannot executed directly. See below:  

```php
<?php
    class MyClass
    {
        public $func;

        public function __construct()
        {
            $func = function () {
                return "hello";
            };
        }
    }

    $obj = new MyClass;
    ($obj->func)(); // correct way to execute a function
?>
```

## Extends  

Classes can only inherit to one base class. Methods and properties of parent class can be overriden by redefining it with the same name(this cannot be done if the parent class has declared the method/property as `final`. It is possible to access the overridden method/property using the `parent::` syntax  

**Signature compatibility rules** - When overriding a method, its signature must be compatible with the parent method. A signature is compatible if it respects the `variance` rules, makes a mandatory parameter optional, adds only optional new parameters and doesn't restrict but only relaxes the visibility.

Use the `::class` syntax to perform class name resolution. Very useful for mapping namespaces
```php
<?php
    class MyClass {}
    
    echo MyClass::class, PHP_EOL;
?>
```

TODO: Needs further research on **nullsafe** operator  

