Pattern: Malformed spacing around class body

Issue: -

## Description

This rule checks if empty lines around the bodies of classes match the configuration.

## Examples

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

* [RuboCop - Layout/EmptyLinesAroundClassBody](https://docs.rubocop.org/rubocop/cops_layout.html#layoutemptylinesaroundclassbody)
* [https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies](https://github.com/bbatsov/ruby-style-guide#empty-lines-around-bodies)
