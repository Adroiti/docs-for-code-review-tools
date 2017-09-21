Pattern: Use of tab character

Issue: -

## Description

Checks that there are no tab characters (`'\t'`) in the source code. 

Rationale: 

  - Developers should not need to configure the tab width of their text editors in order to be able to read source code. 
  - In a distributed development environment where diffs are sent to the mailing lists by both developers and the version control system (which sends commit log messages), the use tabs makes it impossible to preserve legibility.

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.file.FileTabChecker&quot; level=&quot;warning&quot;/&gt;</pre>
<a name="org_scalastyle_file_HeaderMatchesChecker" />

## Further Reading

* [Scalastyle - FileTab](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_file_FileTabChecker)