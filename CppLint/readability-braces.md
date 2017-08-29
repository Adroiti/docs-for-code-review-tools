Pattern: Malformed curly braces

Issue: -

## Description

In general, curly braces are not required for single-line statements, but they are allowed if you like them; conditional or loop statements with complex conditions or statements may be more readable with curly braces. Some projects require that an `if` must always always have an accompanying brace.
    
    
    if (condition)
      DoSomething();  // 2 space indent.

    if (condition) {
      DoSomething();  // 2 space indent.
    }
    

However, if one part of an `if`-`else` statement uses curly braces, the other part must too:
    
    
    // Not allowed - curly on IF but not ELSE
    if (condition) {
      foo;
    } else
      bar;

    // Not allowed - curly on ELSE but not IF
    if (condition)
      foo;
    else {
      bar;
    }
    
    // Curly braces around both IF and ELSE required because
    // one of the clauses used braces.
    if (condition) {
      foo;
    } else {
      bar;
    }
	
	
## Further Reading

* [Google C++ Style Guide - Conditionals](https://google.github.io/styleguide/cppguide.html#Conditionals)	
