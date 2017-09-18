Pattern: Missing `other` name for binary operator

Issue: -

## Description

This rule makes sure that certain binary operator methods have their sole parameter named `other`.

## Examples

```ruby
# bad
def +(amount); end

# good
def +(other); end
```

## Further Reading

* [RuboCop - Naming/BinaryOperatorParameterName](https://rubocop.readthedocs.io/en/latest/cops_naming/#namingbinaryoperatorparametername)
* [https://github.com/bbatsov/ruby-style-guide#other-arg](https://github.com/bbatsov/ruby-style-guide#other-arg)
