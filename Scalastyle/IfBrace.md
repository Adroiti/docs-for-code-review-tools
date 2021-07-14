Pattern: `if` without braces

Issue: -

## Description

Some people find if clauses with braces easier to read. The `singleLineAllowed` property allows if constructions of the type:

    if (bool_expression) expression1 else expression2

The `doubleLineAllowed` property allows if constructions of the type:

    if (bool_expression) expression1
    else expression2

Note: If you intend to enable only if expressions in the format below, disable the `IfBraceChecker` altogether.

    if (bool_expression)
      expression1
    else
      expression2

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>singleLineAllowed</td>
        <td>Single Line Allowed</td>
        <td>boolean</td>
        <td>true</td>
      </tr><tr><td>doubleLineAllowed</td>
        <td>Double Line Allowed</td>
        <td>boolean</td>
        <td>false</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.IfBraceChecker" level="warning">
 <parameters>
  <parameter name="singleLineAllowed">true</parameter>
  <parameter name="doubleLineAllowed">false</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_IllegalImportsChecker" />

## Further Reading

* [Scalastyle - IfBrace](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_IfBraceChecker)