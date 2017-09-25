Pattern: Ungrouped imports

Issue: -

## Description

If imports are spread throughout the file, knowing what is in scope at any one place can be difficult to work out.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ImportGroupingChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_ImportOrderChecker" />

## Further Reading

* [Scalastyle - ImportGrouping](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_ImportGroupingChecker)