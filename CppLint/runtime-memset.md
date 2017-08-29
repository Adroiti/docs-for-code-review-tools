Pattern: Wrong use of `memset()`

Issue: -

## Description

Use `sizeof(varname)` when you take the size of a particular variable. `sizeof(varname)` will update appropriately if someone changes the variable type either now or later. You may use `sizeof(type)` for code unrelated to any particular variable, such as code that manages an external or internal data format where a variable of an appropriate C++ type is not convenient.
    
Example of **incorrect** code:

```cpp
Struct data;
memset(&data, 0, sizeof(data));
```
	
Example of **correct** code:
 
```cpp
memset(&data, 0, sizeof(Struct));
```

## Further Reading

* [Google C++ Style Guide - sizeof](https://google.github.io/styleguide/cppguide.html#sizeof)