Pattern: Malformed spacing around method body

Issue: -

## Description

This rule checks if empty lines exist around the bodies of methods.

## Examples

```ruby
# good

def foo
  ...
end

# bad

def bar

  ...

end
```

## Further Reading

* [RuboCop - Layout/EmptyLinesAroundMethodBody](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutemptylinesaroundmethodbody)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies)
