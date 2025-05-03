
# Interfaces  

Defined in the same way as class. All methods declared in an interface must be public  

To implement an interface the `implement` keyword is used. Interfaces can be extended similar to classes.

Interfaces can declare properties inside as long as it is publicly readable and writable  

For abstract classes that implements an interface, the abstract class doesn't necessarily need to implement the methods and properties of the interface, the extending class should do that.

*Note:* `phpactor` doesn't seem to currently support properties inside interface  

When extending and implementing class and interface, order of keyword is important. `extends` should be ahead of `implements`. See below:  

```php
<?php
    class A { }
    
    interface B { }
    
    interface C { }

    class D extends A impelements B, C { }
?>
```
