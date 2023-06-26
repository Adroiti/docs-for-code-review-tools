Pattern: Exception class it not immutable

Issue: -

## Description

Ensures that exception classes (classes with names conforming to some regular expression and explicitly extending classes with names conforming to other regular expression) are immutable, that is, that they have only final fields. 

The current algorithm is very simple: it checks that all members of exception are final. The user can still mutate an exception's instance (e.g. Throwable has a method called `setStackTrace` which changes the exception's stack trace). But, at least, all information provided by this exception type is unchangeable. 

Rationale: Exception instances should represent an error condition. Having non final fields not only allows the state to be modified by accident and therefore mask the original condition but also allows developers to accidentally forget to set the initial state. In both cases, code catching the exception could draw incorrect conclusions based on the state. 

## Examples

To configure the check: 


```xml
<module name="MutableException"/>
```

## Further Reading

* [checkstyle - MutableException](https://checkstyle.sourceforge.io/checks/design/mutableexception.html#MutableException)
