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

* [RuboCop - Layout/EmptyLinesAroundMethodBody](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylinesaroundmethodbody)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies)
