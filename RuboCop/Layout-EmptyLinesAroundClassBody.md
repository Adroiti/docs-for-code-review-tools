Pattern: Layout/EmptyLinesAroundClassBody

Issue: -

## Description

This cops checks if empty lines around the bodies of classes match
the configuration.

### Example

```ruby
EnforcedStyle: empty_lines

# good

class Foo

   def bar
     ...
   end

end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | no_empty_lines
SupportedStyles | empty_lines, empty_lines_except_namespace, empty_lines_special, no_empty_lines

## Further Reading

* [RuboCop - Layout/EmptyLinesAroundClassBody](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutemptylinesaroundclassbody)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies)
