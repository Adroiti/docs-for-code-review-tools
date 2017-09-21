Pattern: Import from illegal package

Issue: -

## Description

Avoid importing from package that contains internal APIs: they are subject to change in a **undocumented** or **unsupported** way and they are bound to a specific JRE/JDK (e.g. Sun), limiting portability of your programs.

Prefer a public, documented and specified class instead.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>illegalImports</td>
        <td>Illegal Imports</td>
        <td>string</td>
        <td>sun._,java.awt._</td>
      </tr></table>

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.IllegalImportsChecker&quot; level=&quot;warning&quot;/&gt;</pre>
<a name="org_scalastyle_scalariform_ImportGroupingChecker" />

## Further Reading

* [Scalastyle - IllegalImports](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_IllegalImportsChecker)