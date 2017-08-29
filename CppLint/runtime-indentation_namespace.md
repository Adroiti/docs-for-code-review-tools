Pattern: Indent within namespace

Issue: -

## Description

The contents of namespaces should not be indented. For example, use:
    
    
    namespace {

    void foo() {  // Correct.  No extra indentation within namespace.
      ...

    }

    }  // namespace

    

Do not indent within a namespace:
    
    
    namespace {

      // Wrong.  Indented when it should not be.
      void foo() {
        ...

      }

    }  // namespace


## Further Reading

* [Google C++ Style Guide - Namespace Formatting](https://google.github.io/styleguide/cppguide.html#Namespace_Formatting)
