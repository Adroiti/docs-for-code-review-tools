Pattern: Use of forward declaration

Issue: -

## Description

Avoid using forward declarations where possible. Just `#include` the headers you need:
  
  - Forward declarations can hide a dependency, allowing user code to skip necessary recompilation when headers change.
  - A forward declaration may be broken by subsequent changes to the library. Forward declarations of functions and templates can prevent the header owners from making otherwise-compatible changes to their APIs, such as widening a parameter type, adding a template parameter with a default value, or migrating to a new namespace.
  - Forward declaring symbols from namespace `std::` yields undefined behavior.
  - It can be difficult to determine whether a forward declaration or a full `#include` is needed. Replacing an `#include` with a forward declaration can silently change the meaning of code: 
    
	
          // b.h:
          struct B {};
          struct D : B {};

          // good_user.cc:
          #include "b.h"
          void f(B*);
          void f(void*);
          void test(D* x) { f(x); }  // calls f(B*)

          

If the `#include` was replaced with forward decls for `B` and `D`, `test()` would call `f(void*)`. 
  - Forward declaring multiple symbols from a header can be more verbose than simply `#include`ing the header.
  - Structuring code to enable forward declarations (e.g. using pointer members instead of object members) can make the code slower and more complex.
  
## Further Reading

* [Google C++ Style Guide - Forward Declarations](https://google.github.io/styleguide/cppguide.html#Forward_Declarations)
  
