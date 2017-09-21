Pattern: Use of underscore import

Issue: -

## Description

Importing all classes from a package or static members from a class leads to tight coupling between packages or classes and might lead to problems when a new version of a library introduces name clashes.

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.UnderscoreImportChecker&quot; level=&quot;warning&quot;&gt;
 &lt;parameters&gt;
  &lt;parameter name=&quot;ignoreRegex&quot;&gt;collection\.JavaConverters\._|scala\.concurrent\.duration\._&lt;/parameter&gt;
 &lt;/parameters&gt;
&lt;/check&gt;</pre>
<a name="org_scalastyle_scalariform_UppercaseLChecker" />

## Further Reading

* [Scalastyle - UnderscoreImport](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_UnderscoreImportChecker)