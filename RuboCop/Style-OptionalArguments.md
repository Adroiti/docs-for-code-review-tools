Pattern: Malformed optional arguments

Issue: -

## Description

This rule checks for optional arguments to methods that do not come at the end of the argument list. Ruby has some unexpected results when calling methods that have optional arguments at the front of the list.

## Examples

```ruby
# bad
def foo(a = 1, b, c)
end

# good
def baz(a, b, c = 1)
end

def foobar(a = 1, b = 2, c = 3)
end
```

## Further Reading

* [RuboCop - Style/OptionalArguments](https://docs.rubocop.org/rubocop/cops_style.html#styleoptionalarguments)
* [https://github.com/bbatsov/ruby-style-guide#optional-arguments](https://github.com/bbatsov/ruby-style-guide#optional-arguments)
