Pattern: Use of parameter assignment

Issue: -

## Description

Disallows assignment of parameters.

Rationale: Parameter assignment is often considered poor programming practice. Forcing developers to declare parameters as final is often onerous. Having a check ensure that parameters are never assigned would give the best of both worlds. 

## Examples

To configure the check: 


```xml
<module name="ParameterAssignment"/>
```

## Further Reading

* [checkstyle - ParameterAssignment](https://checkstyle.sourceforge.io/checks/coding/parameterassignment.html#ParameterAssignment)
