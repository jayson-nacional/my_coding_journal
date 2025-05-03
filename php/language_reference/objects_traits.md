
# Traits  

Used for code reuse in single inheritance language such as PHP.

```php
<?php
    trait TraitA
    {
        public function sayHello()
        {
            echo "hello!", PHP_EOL;
        }
    }

    trait TraitB
    {
        public function sayHi()
        {
            echo "hi!", PHP_EOL;
        }
    }

    class ClassC
    {
        use TraitA, TraitB;
    }

    $obj = new ClassC;
    $obj->sayHello(); // hello!
    $obj->sayHi(); // hi!
?>
```  

## Precedence  

An inherited member from a base class is overriden by a member inserted by a Trait. The precedence order is that members from the current class override Trait methods, which in turn override inherited methods.  

## Conflict Resolution

In case of function with the same name that exists in multiple used traits, error is throw. This is resolved by using the `insteadof` operator

```php
<?php
    trait TraitA
    {
        public function greet()
        {
            echo "Good morning!", PHP_EOL;
        }
    }

    trait TraitB
    {
        public function greet()
        {
            echo "Good afternoon!", PHP_EOL;
        }
    }

    class ClassC
    {
        use TraitA, TraitB
        {
            TraitA::greet instead of TraitB;
        }
    }
?>
```

## Changing Method Visibility  

Using the `as` syntax, metohd visibility can be changed  

```php
<?php
    trait HelloWorld
    {
        public function sayHello()
        {
            echo "Hello, World!", PHP_EOL;
        }
    }

    // sayHello becomes protected
    class MyClass
    {
        use HelloWorld { sayHello as protected; }
    }

    // sayHello visibility not changed
    // new private method is reference myPrivateSayHello
    class MyClass2
    {
        use HelloWorld { sayHello as private myPrivateSayHello; }
    }
?>
```

## Traits Composed from Traits  

```php
<?php
    trait TraitA
    {
        public function foo() { }
    }

    trait TraitB
    {
        public function bar() { }
    }
    
    trait TraitC
    {
        use TraitA, TraitB;
    }
?>
```  

*Note:* Traits support declaration of `abstract` methods  

Traits also support static methods and properties  

TODO: learn more about the use cases of traits
