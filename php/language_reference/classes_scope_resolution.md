
# Scope Resolution Operator  

Paamayim Nekodutayim operator(::) - in simple terms "the double colon"  

```php
<?php
    class MyClass
    {
        public const CONST_VALUE = 123;
    }

    class SubClass extends MyClass
    {
        public static $my_static = "test static variable";

        public static function doubleColon()
        {
            echo parent::CONST_VALUE, PHP_EOL;
            echo self::$my_static
        }
    }
?>
```  

*Note:* Use `$this` to refer to the current object. Use self to refer to the current class. In other words, use `$this->member` for non-static members,use self::$member for static members  


