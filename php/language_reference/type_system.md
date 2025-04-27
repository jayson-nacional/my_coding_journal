
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

---

**Type-juggling**  

: as php is dynamically typed, the interpreter automatically converts the value into a type that supports the operation  

To get the type and value of an expression use the `var_dump()` function, use `get_debug_type()` just to get the type.


# Atomic Types  

Built-in types and integrated with the language, cannot be recreated.  

---

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

---

**User-defined Types**  
- Interfaces
- Classes
- Enumerations

---

**Callable type**  

: are usually functions  


# Composite Types  

Combination of multiple atomic types  

---

**Intersection Types**  

: satisfies multiple type declarations. Joined by ampsersand symbol(&). Intersection of Type T,U, and V is expressed as `T&U&V`  

---

**Union Types**  

: accepts multiple type declarations. Joined by the pipe(|) symbol. Union of Type T,U, and V is expressed as `T|U|V`  

---

**Type Aliases**

: mixed => object|resource|array|string|float|int|bool  

: iterable => Traversible|array  


# NULL  

Unit type as it has only one value (null/NULL - case insensitive)  

`undefined` and result of `unset()` is null  

Use `is_null()` to check if an expression results to null  


# Booleans  

Has two values - true or false (case-insensitive)  

When a value is used in a control structure, it is automatically juggled to its boolean equivalent, casting is not needed.  
**Values which are converted false**  
- boolean `default` is false
- integer 0
- floats 0.0 and -0.0
- empty string "" and string "0"
- array with zero elements ([])
- NULL
- TODO: Analyze => Internal objects that overload their casting behaviour to bool. For example: SimpleXML objects created from empty elements without attributes.  

*Every other value is considered true - including `resource` and `NAN`*
