Pattern: Shadowed argument

Issue: -

## Description

This rule checks for arguments that were shadowed by local variables before they were used.

## Examples

```ruby
# bad

do_something do |foo|
  foo = 42
  puts foo
end

def do_something(foo)
  foo = 42
  puts foo
end
```
```ruby
# good

do_something do |foo|
  foo = foo + 42
  puts foo
end

def do_something(foo)
  foo = foo + 42
  puts foo
end

def do_something(foo)
  puts foo
end
```

## Default configuration

Attribute | Value
--- | ---
IgnoreImplicitReferences | `false`

## Further Reading

* [RuboCop - Lint/ShadowedArgument](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintshadowedargument)
