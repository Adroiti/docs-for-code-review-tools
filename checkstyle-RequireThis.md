Pattern: Missing `this.` for method or instance variable

Issue: -

## Description

Checks that references to instance variables and methods of the present object are explicitly of the form `this.varName` or `this.methodName(args)` and that those references don't rely on the default behavior when `this.` is absent. 

Warning: the check is very controversial if `validateOnlyOverlapping` option is set to 'false' and not that actual nowadays. 

Rationale: 

  1. The same notation/habit for C++ and Java (C++ have global methods, so having `this.` do make sense in it to distinguish call of method of class instead of global). 
  2. Non-IDE development (ease of refactoring, some clearness to distinguish static and non-static methods). 

## Examples

To configure the default check: 
    
    
    <module name="RequireThis"/>
            

To configure to check the `this` qualifier for fields only: 
    
    
    <module name="RequireThis">
        <property name="checkMethods" value="false"/>
    </module>
            

Examples of how the check works if validateOnlyOverlapping option is set to true: 
    
    
    public static class A {
      private int field1;
      private int field2;
    
      public A(int field1) {
        // Overlapping by constructor argument.
        field1 = field1; // violation: Reference to instance variable "field1" needs "this".
        field2 = 0;
      }
    
      void foo3() {
        String field1 = "values";
        // Overlapping by local variable.
        field1 = field1; // violation:  Reference to instance variable "field1" needs "this".
      }
    }
    
    public static class B {
      private int field1;
    
      public A(int f) {
        field1 = f;
      }
    
      String addSuffixToField(String field1) {
        // Overlapping by method argument. Equal to "return field1 = field1 + "suffix";"
        return field1 += "suffix"; // violation: Reference to instance variable "field1" needs "this".
      }
    }
           

Please, be aware of the following logic, which is implemented in the check: 

1) If you arrange `this` in your code on your own, the check will not raise violation for variables which use `this` to reference a class field, for example: 
    
    
    public class C {
      private int scale;
      private int x;
      public void foo(int scale) {
        scale = this.scale; // no violation
        if (scale > 0) {
          scale = -scale; // no violation
        }
        x *= scale;
      }
    }
           

2) If method parameter is returned from the method, the check will not raise violation for returned variable/parameter, for example: 
    
    
    public class D {
      private String prefix;
      public String modifyPrefix(String prefix) {
        prefix = "^" + prefix + "$" // no violation (modification of parameter)
        return prefix; // modified method parameter is returned from the method
      }
    }
           

Examples of how the check works if validateOnlyOverlapping option is set to false: 
    
    
    public static class A {
      private int field1;
      private int field2;
    
      public A(int field1) {
        field1 = field1; // violation: Reference to instance variable "field1" needs "this".
        field2 = 0; // violation: Reference to instance variable "field2" needs "this".
        String field2;
        field2 = "0"; // No violation. Local var allowed
      }
    
      void foo3() {
        String field1 = "values";
        field1 = field1; // violation:  Reference to instance variable "field1" needs "this".
      }
    }
    
    public static class B {
      private int field1;
    
      public A(int f) {
        field1 = f; // violation:  Reference to instance variable "field1" needs "this".
      }
    
      String addSuffixToField(String field1) {
        return field1 += "suffix"; // violation: Reference to instance variable "field1" needs "this".
      }
    }
    
    // If the variable is locally defined, there won't be a violation provided the variable doesn't overlap.
    class C {
      private String s1 = "foo1";
      String s2 = "foo2";
    
      C() {
          s1 = "bar1"; // Violation. Reference to instance variable 's1' needs "this.".
          String s2;
          s2 = "bar2"; // No violation. Local var allowed.
          s2 += s2; // Violation. Overlapping. Reference to instance variable 's2' needs "this.".
      }
    }

## Further Reading

* [checkstyle - RequireThis](http://checkstyle.sourceforge.net/config_coding.html#RequireThis)