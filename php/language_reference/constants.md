
# Constants  

Identifier for simple value, where that value doesn't change during the execution (except for magic constants)  

## Syntax  

Constants are defined either using the `const` keyword or using the `define()` function - takes two arguments, name and value. Using `const` has limitations as it can only take scalar types (bool, int, float, string, and array with items that are all scalar  

To get the constant value, just use the constant name as reference without adding the dollar symbol like how variables work. It's also possible to use the `constant()` function if the names are obtained dynamically. Use the `get_defined_functions()` to get the list of all defined constants.  


## Predefined Constants  

Constants that are built-in to PHP (i.e. `__FUNCTION__`, `__METHOD__`)


## Magic Constants  

Default constants defined by PHP. In most cases, this are only pointing to external references.  
`__DIR__` -> directory of the file
