Pattern: Use of magic number

Issue: -

## Description

Suggests using constant for [magic numbers](https://en.wikipedia.org/wiki/Magic_number_(programming)#Unnamed_numerical_constants) and string literals.

## Configuration

* `maxLitCount` : (string) maximum number of instances of a string literal that are tolerated before warn.
* `allowStr`: (string) comma-separated list of allowed string literals
* `allowInts`: (string) comma-separated list of allowed integers
* `allowFloats`: (string) comma-separated list of allowed floats

## Example:

```toml
[rule.add-constant]
  arguments = [{maxLitCount = "3",allowStrs ="\"\"",allowInts="0,1,2",allowFloats="0.0,0.,1.0,1.,2.0,2."}]
```

## Further Reading

* [Revive - add-constant](https://revive.run/r#add-constant)