Pattern: Layout/EmptyLineBetweenDefs

Issue: -

## Description

This cop checks whether method definitions are
separated by one empty line.

`NumberOfEmptyLines` can be and integer (e.g. 1 by default) or
an array (e.g. [1, 2]) to specificy a minimum and a maximum of
empty lines.

`AllowAdjacentOneLineDefs` can be used to configure is adjacent
one line methods definitions are an offense

### Example

```ruby
# bad
def a
end
def b
end
```
```ruby
# good
def a
end

def b
end
```

## Default configuration

Attribute | Value
--- | ---
AllowAdjacentOneLineDefs | false
NumberOfEmptyLines | 1

## Further Reading

* [RuboCop - Layout/EmptyLineBetweenDefs](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutemptylinebetweendefs)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-between-methods](https://github.com/bbatsov/ruby-style-guide#empty-lines-between-methods)
