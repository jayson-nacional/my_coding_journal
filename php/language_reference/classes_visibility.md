
# Visibility  

Can be implemented using the keywords `public`, `protected`, and `private`  

**public** - can be accessed everywhere  

**protected** - can be accessed by inheritance and parent classes  

**private** - can only be accessed inside the class where it is defined  


## Asymmetric Property Visibility  

Using visibility modifiers against property `get` and `set` methods  

```php
<?php
    class Book
    {
        public function __construct(
            public private(set) string $title;
            public protected(set) string $author;
            protected private(set) int $pubYear;
        ) { }
    }

    class SpecialBook extends Book
    {
        public function update(string $author, int $year): void
        {
            $this->author = $author;
            $this->pubyear = $year;
        }
    }


    $b = new Book("How to PHP", "Peter H. Peterson", 2024);
    
    echo $b->title; // works
    echo $b->author; // works
    echo $b->pubYear; // Fatal Error

    $b->title = "PHP Test Book"; // Fatal Error
    $b->author = "John Smith"; // Fatal Error
    $b->pubYear = 2025; // Fatal Error
?>
```  

## Asymmetric Property Inheritance  

```php
<?php
    class Book
    {
        protected string $title;
        public protected(set) string $author;
        protected private(set) int $pubYear;
    }

    class SpecialBook extends Book
    {
        public protected(set) $title; // Ok, as reading and writing is wider
        public string $author; // Ok, as reading is the same and writing is wider
        public protected(set) int $pubYear; // Fatal Error, private(set) is considered final
    }
?>
```  

## Method Visibility  

Uses the same modifiers as properties, `public`, `protected`, and `private`


## Constants Visibility  

Works the same way as properties and methods
