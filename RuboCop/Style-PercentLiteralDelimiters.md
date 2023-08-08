Pattern: Malformed `%`-literal delimiter

Issue: -

## Description

This rule enforces the consistent usage of `%`-literal delimiters.

Specify the `default` key to set all preferred delimiters at once. You can continue to specify individual preferred delimiters to override the default.

## Examples

```ruby
# Style/PercentLiteralDelimiters:
#   PreferredDelimiters:
#     default: '[]'
#     '%i':    '()'

# good
%w[alpha beta] + %i(gamma delta)

# bad
%W(alpha #{beta})

# bad
%I(alpha beta)
```

## Default configuration

Attribute | Value
--- | ---
PreferredDelimiters | {"default"=>"()", "%i"=>"[]", "%I"=>"[]", "%r"=>"{}", "%w"=>"[]", "%W"=>"[]"}

## Further Reading

* [RuboCop - Style/PercentLiteralDelimiters](https://docs.rubocop.org/rubocop/cops_style.html#stylepercentliteraldelimiters)
* [https://github.com/bbatsov/ruby-style-guide#percent-literal-braces](https://github.com/bbatsov/ruby-style-guide#percent-literal-braces)
