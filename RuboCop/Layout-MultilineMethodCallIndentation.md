Pattern: Malformed indentation of multi-line method call

Issue: -

## Description

This rule checks the indentation of the method name part in method calls that span more than one line.

## Examples

```ruby
# bad
while myvariable
.b
  # do something
end

# good, EnforcedStyle: aligned
while myvariable
      .b
  # do something
end

# good, EnforcedStyle: aligned
Thing.a
     .b
     .c

# good, EnforcedStyle:    indented,
        IndentationWidth: 2
while myvariable
  .b

  # do something
end

# good, EnforcedStyle:    indented_relative_to_receiver,
        IndentationWidth: 2
while myvariable
        .a
        .b

  # do something
end

# good, EnforcedStyle:    indented_relative_to_receiver,
        IndentationWidth: 2
myvariable = Thing
               .a
               .b
               .c
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | aligned
SupportedStyles | aligned, indented, indented_relative_to_receiver
IndentationWidth |

## Further Reading

* [RuboCop - Layout/MultilineMethodCallIndentation](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutmultilinemethodcallindentation)
