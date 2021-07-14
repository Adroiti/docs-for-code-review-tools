Pattern: File does not end with newline

Issue: -

## Description

Any source files and text files in general should end with a line separator to let others easily add new content at the end of file.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.file.NewLineAtEofChecker" level="warning"/>
```
<a name="org_scalastyle_file_NoNewLineAtEofChecker" />

## Further Reading

* [Scalastyle - NewLineAtEof](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_file_NewLineAtEofChecker)