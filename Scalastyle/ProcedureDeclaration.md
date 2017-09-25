Pattern: Missing `=` for procedure declaration

Issue: -

## Description

A procedure style declaration can cause confusion - the developer may have simply forgotten to add a `=`, and now their method returns Unit rather than the inferred type:

```scala
def foo() { println("hello"); 5 }
def foo() = { println("hello"); 5 }
```


This rule raises a warning with the first line. To fix it, use an explicit return type, or add a `=` before the body.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ProcedureDeclarationChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_PublicMethodsHaveTypeChecker" />

## Further Reading

* [Scalastyle - ProcedureDeclaration](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_ProcedureDeclarationChecker)