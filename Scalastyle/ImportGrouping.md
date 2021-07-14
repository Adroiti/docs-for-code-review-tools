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

* [Scalastyle - ImportGrouping](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_ImportGroupingChecker)