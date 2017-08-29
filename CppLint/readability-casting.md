Pattern: Missing C++-style cast

Issue: -

## Description

The problem with C casts is the ambiguity of the operation; sometimes you are doing a conversion (e.g., (int)3.5) and sometimes you are doing a cast (e.g., (int)"hello"). Brace initialization and C++ casts can often help avoid this ambiguity. Additionally, C++ casts are more visible when searching for them.

Do not use C-style casts. Instead, use these C++-style casts when explicit type conversion is necessary. 

  - Use brace initialization to convert arithmetic types (e.g. `int64{x}`). This is the safest approach because code will not compile if conversion can result in information loss. The syntax is also concise.
  - Use `static_cast` as the equivalent of a C-style cast that does value conversion, when you need to explicitly up-cast a pointer from a class to its superclass, or when you need to explicitly cast a pointer from a superclass to a subclass. In this last case, you must be sure your object is actually an instance of the subclass.
  - Use `const_cast` to remove the `const` qualifier (see const).
  - Use `reinterpret_cast` to do unsafe conversions of pointer types to and from integer and other pointer types. Use this only if you know what you are doing and you understand the aliasing issues. 
  
  
## Further Reading

* [Google C++ Style Guide - Casting](https://google.github.io/styleguide/cppguide.html#Casting)	
