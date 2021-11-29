Pattern: Use of unsafe `IO.*` method

Issue: -

## Description

Checks for the first argument to `IO.read`, `IO.binread`, `IO.write`, `IO.binwrite`,
`IO.foreach`, and `IO.readlines`.

If argument starts with a pipe character (`'|'`) and the receiver is the `IO` class,
a subprocess is created in the same way as `Kernel#open`, and its output is returned.
`Kernel#open` may allow unintentional command injection, which is the reason these
`IO` methods are a security risk.
Consider to use `File.read` to disable the behavior of subprocess invocation.

### Safety

This rule is unsafe because false positive will occur if the variable passed as
the first argument is a command that is not a file path.

## Examples

```ruby
# bad
IO.read(path)
IO.read('path')

# good
File.read(path)
File.read('path')
IO.read('| command') # Allow intentional command invocation.
```

## Further Reading

* [RuboCop - Security/IoMethods](https://docs.rubocop.org/rubocop/cops_security.html#securityiomethods)
