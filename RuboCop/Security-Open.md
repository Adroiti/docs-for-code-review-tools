Pattern: Use of `Kernel#open`

Issue: -

## Description

`Kernel#open` enables not only file access but also process invocation by prefixing a pipe symbol (e.g., `open("| ls")`).  It may lead to
a serious security risk by using variable input to the argument of `Kernel#open`. It would be better to use `File.open` or `IO.popen`
explicitly.

## Examples

```ruby
# bad
open(something)

# good
File.open(something)
IO.popen(something)
```

## Further Reading

* [RuboCop - Security/Open](https://rubocop.readthedocs.io/en/latest/cops_security/#securityopen)
