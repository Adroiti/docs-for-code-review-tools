Pattern: Inconsistent indentation

Issue: -

## Description

This rule checks for inconsistent indentation.

## Examples

```ruby
class A
  def test
    puts 'hello'
     puts 'world'
  end
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | normal
SupportedStyles | normal, rails

## Further Reading

* [RuboCop - Layout/IndentationConsistency](https://docs.rubocop.org/rubocop/cops_layout.html#layoutindentationconsistency)
* [https://github.com/bbatsov/ruby-style-guide#spaces-indentation](https://github.com/bbatsov/ruby-style-guide#spaces-indentation)
