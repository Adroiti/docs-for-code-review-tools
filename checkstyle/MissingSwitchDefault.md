Pattern: Missing switch `default` clause

Issue: -

## Description

This rule enforces to use default case in every `switch` statement.

Rationale:
- To 'catch' an unexpected value. Even if the developer is sure that all currently possible cases are covered, this should be expressed in the default branch, e.g. by using an assertion. This way the code is protected against later changes.
- To handle 'default' actions, where the cases are for special behavior.
- To show someone reading your code that you've covered that case.

## Default configuration

```xml
<module name="MissingSwitchDefault"/>
```

## Examples

Example of **incorrect** code:

```java
switch(type)
{
    case 1:
        doSomething();
        break;
    case 2:
        doSomethingElse();
        break;
}
```

Example of **correct** code:

```java
switch(type)
{
    case 1:
        doSomething();
        break;
    case 2:
        doSomethingElse();
        break;
    default:
        // unknown type! 
        // there should probably be some error-handling here, maybe an exception
}
```

## Further Reading

* [Google Java Style Guide - Switch statements](https://google.github.io/styleguide/javaguide.html#s4.8.4-switch)
* [checkstyle - MissingSwitchDefault](https://checkstyle.sourceforge.io/checks/coding/missingswitchdefault.html#MissingSwitchDefault)
