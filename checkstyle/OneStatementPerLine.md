Pattern: Multiple statements in one line

Issue: -

## Description

Prefer using one statement per line to improve code readability.

The following statement types are checked: 
- variable declaration
- empty
- assignment
- expression
- increment
- object creation
- `import`
- `for` loop
- `break`
- `continue`
- `return`

## Default configuration

```xml
<module name="OneStatementPerLine"/>
```

## Examples

Example of **incorrect** code:

```python
import java.io.EOFException; import java.io.BufferedReader;
```

Example of **correct** code:

```python
import java.io.EOFException;
import java.io.BufferedReader;
```

## Further Reading

* [Google Java Style Guide - One statement per line](https://google.github.io/styleguide/javaguide.html#s4.3-one-statement-per-line)
* [checkstyle - OneStatementPerLine](https://checkstyle.sourceforge.io/checks/coding/onestatementperline.html#OneStatementPerLine)
