Pattern: Use of `it` without argument

Issue: -

## Description

`it` calls without arguments will refer to the first block param in Ruby 3.4. So use `it()` or `self.it` to ensure compatibility.

## Examples

```ruby
# bad
do_something { it }

# good
do_something { it() }
do_something { self.it }
```

## Further Reading

* [RuboCop - Lint/ItWithoutArgumentsInBlock](https://docs.rubocop.org/rubocop/cops_lint.html#lintitwithoutargumentsinblock)
