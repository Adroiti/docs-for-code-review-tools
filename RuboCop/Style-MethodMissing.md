Pattern: Use of `method_missing`

Issue: -

## Description

This cop checks for the presence of `method_missing` without also defining `respond_to_missing?` and falling back on `super`.

### Example

```ruby
#bad
def method_missing(...)
  ...
end

#good
def respond_to_missing?(...)
  ...
end

def method_missing(...)
  ...
  super
end
```

## Further Reading

* [RuboCop - Style/MethodMissing](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemethodmissing)
* [https://github.com/bbatsov/ruby-style-guide#no-method-missing](https://github.com/bbatsov/ruby-style-guide#no-method-missing)
