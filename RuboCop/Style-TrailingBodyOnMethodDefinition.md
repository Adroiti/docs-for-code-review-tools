Pattern: Trailing code after method definition

Issue: -

## Description

This rule checks for trailing code after the method definition. Place the first line of a multi-line method definition's body on its own line.

## Examples

```ruby
# bad
def some_method; do_stuff
end

def f(x); b = foo
  b[c: x]
end

# good
def some_method
  do_stuff
end

def f(x)
  b = foo
  b[c: x]
end
```

## Further Reading

* [RuboCop - Style/TrailingBodyOnMethodDefinition](https://docs.rubocop.org/rubocop/cops_style.html#styletrailingbodyonmethoddefinition)
