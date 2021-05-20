Pattern: Parameter assignment in filter closure

Issue: -

## Description

An assignment operator was used on a parameter, or a property or subproperty of the parameter, in a filtering or searching closure. This is usually a typo, and the comparison operator (`==`) was intended.

This rule will check the following filter methods: `find`, `findAll`, `findIndexOf`, `every`, `any`, `filter`, `grep`, `dropWhile` and `takeWhile`.

## Examples

```java
List someList = [1,2,3]
someList.find {it == 2}
someList.find {it = 2}                  // violation, this actually finds 1 instead.
someList.find { int integer ->
	integer == 2
}
someList.find { int integer ->
	integer = 2                         // violation, this actually finds 1 instead.
}
someList.takeWhile { it.name = 42 }     // violation
```

## Further Reading

* [CodeNarc - ParameterAssignmentInFilterClosure](https://codenarc.org/codenarc-rules-basic.html#parameterassignmentinfilterclosure-rule)