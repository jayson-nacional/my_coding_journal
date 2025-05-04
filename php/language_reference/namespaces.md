
# Namespaces  

To define a namespace, use the syntax `namespace my\name;`  

Namespace only affects the following:  
- classes (including abstracts and traits)
- interfaces
- functions
- constants  

Namespace should be declared at the very top of the php file, only below the `declare()`  

Namespaces can also have their sub-level. To do so, see sample `namespace MyProject\Sub\Level;`  

When declaring multiple namespace in a single file, it is recommended to enclose the code in curly braces.  

```php
<?php
    namespace Main\LevelOne
    {
        class MyClass { }
        trait MyTrait { }
        const MYCONST { }
    }
    
    namespace Main\LevelTwo
    {
        class SubClass { }
        trait SubTrait { }
        const SUB_CONST { } 
    }
?>
```  

To get the current namespace, use the global constant `__NAMESPACE__`  

## Aliasing and Importing  

To import a namespace, use the `use` keyword. Imported namespace items can be linked to a new name(like a unix symbolic link) using the keyword `as` followed by the alias.  

```php
<?php
    use My\Full\ClassName as Another;
    
    $object = new Another;
?>
```  

The `use` keyword must be used on the outermost scope of the file(global scope) and cannot be put inside a block as it is processed at compile time.

For readability, namespaces items that are being imported on the same namespace should be grouped together.

```php
<?php
    use Some\Namespace\ClassA;
    use Some\Namespace\ClassB;
    use Some\Namespace\ClassC;
?>
```  

File with no namespace declared would be to be part of global scope

TODO: Learn more about namespace resolution rules


