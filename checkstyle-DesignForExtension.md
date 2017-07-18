Pattern: Possible misuse of class designed for extension

Issue: -

## Description

The check finds classes that are designed for extension (subclass creation). 

Nothing wrong could be with founded classes. This check makes sense only for library project (not an application projects) which care of ideal OOP-design to make sure that class works in all cases even mis-usage. Even in library projects this check most likely will find classes that are designed for extension by somebody. User needs to use suppressions extensively to got a benefit from this check, and keep in suppressions all confirmed/known classes that are deigned for inheritance intentionally to let the check catch only new classes, and bring this to team/user attention. 

ATTENTION: Only user can decide whether a class is designed for extension or not. The check just shows all classes which are possibly designed for extension. If smth inappropriate is found please use suppression. 

ATTENTION: If the method which can be overridden in a subclass has a Javadoc comment (a good practice is to explain its self-use of override-able methods) the check will not rise a violation. The violation can also be skipped if the method which can be overridden in a subclass has one or more annotations that are specified in ignoredAnnotations option. Note, that by default `@Override` annotation is not included in the ignoredAnnotations set as in a subclass the method which has the annotation can also be overridden in its subclass. 

Problem is described at _Effective Java, 2nd Edition by Josh Bloch book, chapter Item 17: Design and document for inheritance or else prohibit it_. 

Some quotes from book: 

> The class must document its self-use of override-able methods. By convention, a method that invokes override-able methods contains a description of these invocations at the end of its documentation comment. The description begins with the phrase "This implementation."

> The best solution to this problem is to prohibit subclassing in classes that are not designed and documented to be safely subclassed. 

> If a concrete class does not implement a standard interface, then you may inconvenience some programmers by prohibiting inheritance. If you feel that you must allow inheritance from such a class, one reasonable approach is to ensure that the class never invokes any of its override-able methods and to document this fact. In other words, eliminate the class's self-use of override-able methods entirely. In doing so, you'll create a class that is reasonably safe to subclass. Overriding a method will never affect the behavior of any other method. 

The check finds classes that have override-able methods (public or protected methods that are non-static, not-final, non-abstract) and have non-empty implementation. 

Rationale: This library design style protects superclasses against being broken by subclasses. The downside is that subclasses are limited in their flexibility, in particular they cannot prevent execution of code in the superclass, but that also means that subclasses cannot corrupt the state of the superclass by forgetting to call the superclass's method. 

More specifically, it enforces a programming style where superclasses provide empty "hooks" that can be implemented by subclasses. 

Example of code that cause violation as it is designed for extension: 


```java
public abstract class Plant {
    private String roots;
    private String trunk;
```

```java
    protected void validate() {
      if (roots == null) throw new IllegalArgumentException("No roots!");
      if (trunk == null) throw new IllegalArgumentException("No trunk!");
    }
```

```java
    public abstract void grow();
}
```

```java
public class Tree extends Plant {
    private List leaves;
```

```java
    @Overrides
    protected void validate() {
      super.validate();
      if (leaves == null) throw new IllegalArgumentException("No leaves!");
    }
```

```java
    public void grow() {
      validate();
    }
}
```
        

Example of code without violation: 


```java
public abstract class Plant {
    private String roots;
    private String trunk;
```

```java
    private void validate() {
        if (roots == null) throw new IllegalArgumentException("No roots!");
        if (trunk == null) throw new IllegalArgumentException("No trunk!");
        validateEx();
    }
```

```java
    protected void validateEx() { }
```

```java
    public abstract void grow();
}
```
        

## Examples

To configure the check: 


```xml
<module name="DesignForExtension"/>
```
        

To configure the check to allow methods which have `@Override` and `@Test` annotations to be designed for extension. 


```xml
<module name="DesignForExtension">
  <property name="ignoredAnnotations" value="Override, Test"/>
</module>
```
        


```java
public class A extends B {
  @Override
  public int foo() {
    return 2;
  }
```

```java
  public int foo2() {return 8;} // violation
}
```

```java
public class B {
  /**
   * This implementation ...
     @return some int value.
   */
  public int foo() {
    return 1;
  }
```

```java
  public int foo3() {return 3;} // violation
}
```

```java
public class FooTest {
  @Test
  public void testFoo() {
     final B b = new A();
     assertEquals(2, b.foo());
  }
```

```java
  public int foo4() {return 4;} // violation
}
```

## Further Reading

* [checkstyle - DesignForExtension](http://checkstyle.sourceforge.net/config_design.html#DesignForExtension)
