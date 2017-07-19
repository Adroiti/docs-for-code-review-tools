Pattern: Missing switch `default` clause

Issue: -

## Description

Checks that switch statement has a `default` clause. 

Rationale: It's usually a good idea to introduce a default case in every switch statement. Even if the developer is sure that all currently possible cases are covered, this should be expressed in the default branch, e.g. by using an assertion. This way the code is protected against later changes, e.g. introduction of new types in an enumeration type. 

## Examples

To configure the check: 


```xml
<module name="MissingSwitchDefault"/>
```

## Further Reading

* [Google Java Style Guide - Switch statements](https://google.github.io/styleguide/javaguide.html#s4.8.4-switch)
* [checkstyle - MissingSwitchDefault](http://checkstyle.sourceforge.net/config_coding.html#MissingSwitchDefault)
