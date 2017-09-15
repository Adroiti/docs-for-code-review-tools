Pattern: Malformed spacing around begin body

Issue: -

## Description

This cops checks if empty lines exist around the bodies of begin-end blocks.

### Example

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

* [RuboCop - Layout/EmptyLinesAroundBeginBody](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutemptylinesaroundbeginbody)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies)
