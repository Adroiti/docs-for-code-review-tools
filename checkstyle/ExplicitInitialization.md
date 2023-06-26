Pattern: Explicit variable initialization

Issue: -

## Description

Checks if any class or object member is explicitly initialized to default for its type value (`null` for object references, zero for numeric types and `char` and `false` for `boolean`. 

Rationale: Each instance variable gets initialized twice, to the same value. Java initializes each instance variable to its default value (0 or null) before performing any initialization specified in the code. So in this case, x gets initialized to 0 twice, and bar gets initialized to null twice. So there is a minor inefficiency. This style of coding is a holdover from C/C++ style coding, and it shows that the developer isn't really confident that Java initializes instance variables to default values. 

## Examples

To configure the check: 


```xml
<module name="ExplicitInitialization"/>
```
        

To configure the check so that it only checks for objects that explicitly initialize to null: 


```xml
<module name="ExplicitInitialization">
    <property name="onlyObjectReferences" value="true"/>
</module>
```
        

Example:


```java
   public class Test {
 private int a = 0;
 private int b = 1;
 private int c = 2;
 

 private boolean a = true;
 private boolean b = false;
 private boolean c = true;
 private boolean d = false;
 private boolean e = false;
 

 private A a = new A();
 private A b = null; // violation
 private C c = null; // violation
 private D d = new D();
 

 int ar1[] = null; // violation
 int ar2[] = new int[];
 int ar3[];
 private Bar<String> bar = null; // violation
 private Bar<String>[] barArray = null; // violation
 

 public static void main( String [] args ) {
 }
   }
```

## Further Reading

* [checkstyle - ExplicitInitialization](https://checkstyle.sourceforge.io/checks/coding/explicitinitialization.html#ExplicitInitialization)
