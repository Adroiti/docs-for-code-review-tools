Pattern: Inconsistent indentation

Issue: -

## Description

This rule checks that the indentation method is consistent. Either tabs only or spaces only are used for indentation.

## Examples

### EnforcedStyle: spaces (default)

```ruby
# bad
# This example uses a tab to indent bar.
def foo
  bar
end

# good
# This example uses spaces to indent bar.
def foo
  bar
end
```

### EnforcedStyle: tabs

```ruby
# bad
# This example uses spaces to indent bar.
def foo
  bar
end

# good
# This example uses a tab to indent bar.
def foo
  bar
end
```

## Further Reading

* [RuboCop - Layout/IndentationStyle](https://docs.rubocop.org/rubocop/cops_layout.html#layoutindentationstyle)
