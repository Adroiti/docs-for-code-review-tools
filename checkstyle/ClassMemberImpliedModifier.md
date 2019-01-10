Pattern: Use of implicit modifier on class members

Issue: -

## Description

Checks for implicit modifiers on nested types in classes. 

Nested enums and interfaces within a class are always `static` and as such the compiler does not require the `static` modifier. This check provides the ability to enforce that the `static` modifier is explicitly coded and not implicitly added by the compiler.
    
    
    public final class Person {
      enum Age {  // violation
        CHILD, ADULT
      }
    }
            

Rationale for this check: Nested enums and interfaces are treated differently from nested classes as they are only allowed to be `static`. Developers should not need to remember this rule, and this check provides the means to enforce that the modifier is coded explicitly. 

## Examples

This example checks that all implicit modifiers on nested interfaces and enums are explicitly specified in classes. 

Configuration: 
    
    
    <module name="ClassMemberImpliedModifier" />
            

Code: 
    
    
    public final class Person {
      static interface Address1 {  // valid
      }
    
      interface Address2 {  // violation
      }
    
      static enum Age1 {  // valid
        CHILD, ADULT
      }
    
      enum Age2 {  // violation
        CHILD, ADULT
      }
    }

## Further Reading

* [checkstyle - ClassMemberImpliedModifier](http://checkstyle.sourceforge.net/config_modifier.html#ClassMemberImpliedModifier)