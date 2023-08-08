Pattern: Missing empty line between method definitions

Issue: -

## Description

This rule checks whether method definitions are separated by one empty line.

`NumberOfEmptyLines` can be and integer (e.g. 1 by default) or
an array (e.g. [1, 2]) to specify a minimum and a maximum of
empty lines.

`AllowAdjacentOneLineDefs` can be used to configure is adjacent
one line methods definitions are an offense

## Examples

```ruby
def some_method
  data = initialize(options)

  
  data.manipulate!

  
  data.result
end


def some_method
  result
end
```

## Default configuration

Attribute | Value
--- | ---
AllowAdjacentOneLineDefs | false
NumberOfEmptyLines | 1

## Further Reading

* [RuboCop - Layout/EmptyLineBetweenDefs](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylinebetweendefs)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-between-methods](https://github.com/bbatsov/ruby-style-guide#empty-lines-between-methods)
