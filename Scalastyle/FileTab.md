Pattern: Use of tab character

Issue: -

## Description

Checks that there are no tab characters (`'\t'`) in the source code. 

Rationale: 

  - Developers should not need to configure the tab width of their text editors in order to be able to read source code. 
  - In a distributed development environment where diffs are sent to the mailing lists by both developers and the version control system (which sends commit log messages), the use tabs makes it impossible to preserve legibility.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.file.FileTabChecker" level="warning"/>
```
<a name="org_scalastyle_file_HeaderMatchesChecker" />

## Further Reading

* [Scalastyle - FileTab](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_file_FileTabChecker)