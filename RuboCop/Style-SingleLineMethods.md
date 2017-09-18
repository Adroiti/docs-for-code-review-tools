Pattern: Single-line method definition

Issue: -

## Description

This rule checks for single-line method definitions. It can optionally accept single-line methods with no body.

## Examples

```ruby
# bad
def too_much; something; something_else; end

# okish - notice that the first ; is required
def no_braces_method; body end

# okish - notice that the second ; is optional
def no_braces_method; body; end

# okish - valid syntax, but no ; makes it kind of hard to read
def some_method() body end

# good
def some_method
  body
end
```

## Default configuration

Attribute | Value
--- | ---
AllowIfMethodIsEmpty | true

## Further Reading

* [RuboCop - Style/SingleLineMethods](https://rubocop.readthedocs.io/en/latest/cops_style/#stylesinglelinemethods)
* [https://github.com/bbatsov/ruby-style-guide#no-single-line-methods](https://github.com/bbatsov/ruby-style-guide#no-single-line-methods)
