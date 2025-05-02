
# Properties  

`$this` is the value of the calling object  

`readonly` properties prevent modification after initialization  

**Dyamic Properties** - If trying to assign to a non-existent property on an object, PHP will automatically create a corresponding property. This dynamically created property can only be accessible on the class instance.  

## Property Hooks  

Also known as "property accessors". This utilizes the `get` and `set` methods to override the read and write behaviors on the property.  

```php
<?php
    class MyClass
    {
        private bool $modified = false;

        public string $foo = "default value" {
            get {
                if ($this->modified) {
                    return $this->foo . " (modified)";
                }

                return $this->foo;
            }
            set(string $value) {
                $this->foo = $value;
                $this->modified = true;
            }
        }
    }
?>
```  

TODO: 
- to learn more about asymmetric property visibility  
- constructor property promotion

## Class Constants  

Accessible using the syntax `Class::[constant name]`

```php
<?php
    class MyClass
    {
        const VALUE = "test value";
    }

    echo MyClass::VALUE, PHP_EOL;
?>
```
