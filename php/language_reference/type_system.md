
# Introduction  

**Built-in Types**  
- null
- bool
- int
- float(floating-point number)
- string
- array
- object
- callable
- resource  

Type-juggling  
: as php is dynamically typed, the interpreter automatically converts the value into a type that supports the operation  

To get the type and value of an expression use the `var_dump()` function, use `get_debug_type()` just to get the type.


# Atomic Types  

Built-in types and integrated with the language, cannot be recreated.  

**Built-in Types**  
- Scalar types: 
    - bool
    - int
    - float
    - string
- array
- object
- resource
- never
- void
- Relative class types: self, parent and static
- Singleton types:
    - false
    - true
- Unit types
    - null  

**User-defined Types**  
- Interfaces
- Classes
- Enumerations

Callable type
: are usually functions  


# Composite Types  

Combination of multiple atomic types  

Intersection Types  
: satisfies multiple type declarations. Joined by ampsersand symbol(&). Intersection of Type T,U, and V is expressed as `T&U&V`  

Union Types  
: accepts multiple type declarations. Joined by the pipe(|) symbol. Union of Type T,U, and V is expressed as `T|U|V`  

Type Aliases
: mixed => object|resource|array|string|float|int|bool
: iterable => Traversible|array
