
# Enumerations 

Is like a class and represent instances of object, common example is the boolean type with only two possible values, `true` and `false`  

## Basic Enumerations  

```php
<?php
    enum Cards
    {
        case Hearts;
        case Diamonds;
        case Clubs;
        case Spades;
    }

    // can be referenced using the double colon (Paamayim Nekudotayim)
?>
```  

## Backed Enumerations  

In some cases, values needs to be mapped on enumerations to be able to represent values which may potentially be coming in from a database. Follow the syntax below  

```php
<?php
    enum Choices:string
    {
        case LetterA = "A";
        case LetterB = "B";
        case LetterC = "C";
        case LetterD = "D";
    }

    // accessible using the syntax Choices::LetterA->value
?>
``` 

TODO: Learn what static return does

Utilizes the `BackedEnum` interface.   
- `BackedEnum::from` => Maps a scalar to an enum instance  
- `BackedEnum::tryFrom` => Maps a scalar to an enum instance or null


## Enumeration Methods  

Enumerations can also contain functions and implement interfaces  

```php
<?php
    interface Colorful
    {
        public function color(): string;
    }

    enum Suit implements Colorful
    {
        case Spades;
        case Hearts;
        case Clubs;
        case Diamonds;
        
        public function color(): string
        {
            return match($this)
            {
                Suit::Hearts, Suit::Diamonds => "Red",
                Suit::Clubs, Suit::Spades => "Black"
            }
        }

        public function shape(): string
        {
            return "Rectangle";
        }
    }

    function paint(Colorful $suit)
    {
        /* ... */
    }

    paint(Suit::Diamonds); // works
    
    print Suit::Diamonds->shape(); // Rectangle
?>
```  

## Enumeration static methods

```php
<?php
    enum Size
    {
        case Small;
        case Medium;
        case Large;

        public static function fromLength(int $length): self
        {
            return match(true) {
                $length < 50 => Size::Small,
                $length < 100 => Size::Medium,
                default => Size::Large
            };
        }
    }
?>
```  

## Enumeration Constants  

```php
<?php
    enum Size
    {
        case Small;
        case Medium;
        case Large;

        public const Huge = self::Large;
    }
?>
```  

## Enumeration Traits  

```php
<?php
    interface Colorful
    {
        public function color(): string;
    }
    
    trait Rectangle
    {
        public function shape(): string {
            return "Rectangle";
        }
    }

    enum Suit implements Colorful
    {
        use Rectangle;

        case Hearts;
        case Diamonds;
        case Clubs;
        case Spades;

        public function color(): string {
            return match($this) {
                Suit::Hearts, Suit::Diamonds => "Red",
                Suit::Clubs, Suit::Spades => "Black"
            }
        }
    }
?>
```  

TODO: Learn more about Enum Values in Constant Expressions  

## Differences from Objects  

- Constructors and Destructors are forbidden
- Inheritance is not supported. Enums may not extend or be extended
- Static or object properties are not allowed
- Cloning an Enum case is not allowed, as cases must be singletone instances
- Magic methods, except(__call, __callStatic, __invoke) are disallowed
- Enums must always be declared before they are used  

## Value Listing  

Use the syntax `Suit::cases()`


## Serialization  

Use both the `serialize()` and `deserialize()` methods


TODO: Learn why enums cannot be extended
