Pattern: Use of covariant `equals()` without overriding `equals(Object)`

Issue: -

## Description

Checks that classes which define a covariant `equals()` method also override method `equals(Object)`.  
Covariant `equals()` \- method that is similar to `equals(Object)`, but with a covariant parameter type (any subtype of Object).  
**Notice**: the enums are also checked, even though they cannot override `equals(Object)`. The reason is to point out that implementing `equals()` in enums is considered an awful practice: it may cause having two different enum values that are equal using covariant enum method, and not equal when compared normally. 

Inspired by [Finding Bugs is Easy, chapter '2.3.1 Bad Covariant Definition of Equals (Eq)'](http://www.cs.nyu.edu/~lharris/papers/findbugsPaper.pdf): 

Java classes may override the `equals(Object)` method to define a predicate for object equality. This method is used by many of the Java runtime library classes; for example, to implement generic containers. 

Programmers sometimes mistakenly use the type of their class `Foo` as the type of the parameter to `equals()`: 


```java
public boolean equals(Foo obj) {...}
```
        

This covariant version of `equals()` does not override the version in the `Object` class, and it may lead to unexpected behavior at runtime, especially if the class is used with one of the standard collection classes which expect that the standard `equals(Object)` method is overridden. 

This kind of bug is not obvious because it looks correct, and in circumstances where the class is accessed through the references of the class type (rather than a supertype), it will work correctly. However, the first time it is used in a container, the behavior might be mysterious. For these reasons, this type of bug can elude testing and code inspections. 

## Examples

To configure the check: 


```xml
<module name="CovariantEquals"/>
```
        

For example: 


```java
class Test {
    public boolean equals(Test i) {  // violation
        return false;
    }
}
```
 

The same class without violations: 


```java
class Test {
    public boolean equals(Test i) {  // no violation
        return false;
    }
 

    public boolean equals(Object i) {
       return false;
    }
}
```

## Further Reading

* [checkstyle - CovariantEquals](https://checkstyle.sourceforge.io/checks/coding/covariantequals.html#CovariantEquals)
