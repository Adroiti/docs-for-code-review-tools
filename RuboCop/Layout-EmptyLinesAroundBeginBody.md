Pattern: Malformed spacing around begin body

Issue: -

## Description

This rule checks if empty lines exist around the bodies of begin-end blocks.

## Examples

```ruby
# good

begin
  ...
end

# bad

begin

  ...

end
```

## Further Reading

* [RuboCop - Layout/EmptyLinesAroundBeginBody](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylinesaroundbeginbody)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies)
