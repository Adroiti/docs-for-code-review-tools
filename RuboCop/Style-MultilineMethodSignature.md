Pattern: Use of multi-line method signature

Issue: -

## Description

This rule checks for method signatures that span multiple lines.

### Examples

```ruby
# good

def test(bar, baz)
end

# bad

def test(bar,
        baz)
end
```

## Further Reading

* [RuboCop - Style/MultilineMethodSignature](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemultilinemethodsignature)
