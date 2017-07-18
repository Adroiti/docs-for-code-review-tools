Pattern: Long source file

Issue: -

## Description

Checks for long source files. 

Rationale: If a source file becomes very long it is hard to understand. Therefore long classes should usually be refactored into several individual classes that focus on a specific task. 

## Examples

To configure the check to accept files with up to 1500 lines: 


```xml
<module name="FileLength">
      <property name="max" value="1500"/>
</module>
```

## Further Reading

* [checkstyle - FileLength](http://checkstyle.sourceforge.net/config_sizes.html#FileLength)
