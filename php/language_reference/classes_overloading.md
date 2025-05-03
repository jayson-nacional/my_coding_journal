
# Overloading  

Provides means to dynamically create properties and methods  

Methods that enable this functionality are called magic methods  

These methods are invoked when non-existent property or method is called upon an instance of an object  

Overloading in PHP hsa different meaning in most of the programming languages  


## Property Overloading  

`public __set(string $name, mixed $value): void`  

=> is run when writing data to inaccessible (protected or private) or non-existing properties  
  
`public __get(string $name): mixed`  

=> is utilized when reading data from inaccessible (protected or private) or non-existing properties  

`public __isset(string $name): bool`  

=> is triggered when calling `isset()` or `empty()` on inaccessible (protected or private) or non-existing properties  

`public __unset(string $name): void`   

=> is invoked when `unset()` is used on inaccessible (protected or private) or non-existing properties  


## Method Overloading  

`public __call(string $name, array $arguments): mixed`  

=> is triggered when invoking inaccessible methods in an object context  

`public static __callStatic(string $name, array $arguments): mixed`  

=> is triggered when invoking inaccessible methods in a static context  
