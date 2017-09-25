Pattern: Unresolved warning comment

Issue: -

## Description

Developers often add comments to code which is not complete or needs review. Most likely you want to fix or review the code, and then remove the comment, before you consider the code to be production ready.

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>words</td>
        <td>Word list</td>
        <td>string</td>
        <td>TODO|FIXME</td>
      </tr></table>

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.TodoCommentChecker" level="warning">
 <parameters>
  <parameter name="words">TODO|FIXME</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_TokenChecker" />

## Further Reading

* [Scalastyle - TodoComment](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_TodoCommentChecker)
