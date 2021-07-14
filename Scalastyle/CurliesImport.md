Pattern: Use of curlies import

Issue: -

## Description

Curlies imports, e.g. `import a.{b, c}`, can lead to annoying merge errors in large code bases that are maintained by lot of developers. This rule allows to ensure that only single imports, no renaming and no hiding imports are used in order to minimize merge errors in import declarations.

### Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.CurliesImportChecker" level="warning"/>
```

## Further Reading

* [Scalastyle - CurliesImport](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_CurliesImportChecker)