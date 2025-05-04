
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

