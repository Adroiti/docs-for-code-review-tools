Pattern: Use of block import

Issue: -

## Description

Block imports (e.g. `import a.{b, c}`) can lead to annoying merge errors in large code bases that are maintained by lot of developers. This rule allows to ensure that only single imports are used in order to minimize merge errors in import declarations.

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.BlockImportChecker&quot; level=&quot;warning&quot;/&gt;</pre>
<a name="org_scalastyle_scalariform_ClassNamesChecker" />

## Further Reading

* [Scalastyle - BlockImport](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_BlockImportChecker)