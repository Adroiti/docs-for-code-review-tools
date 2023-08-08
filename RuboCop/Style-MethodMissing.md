Pattern: Use of `method_missing`

Issue: -

## Description

This rule checks for the presence of `method_missing` without also defining `respond_to_missing?` and falling back on `super`.

## Examples

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

* [RuboCop - Style/MethodMissing](https://docs.rubocop.org/rubocop/cops_style.html#stylemethodmissing)
* [https://github.com/bbatsov/ruby-style-guide#no-method-missing](https://github.com/bbatsov/ruby-style-guide#no-method-missing)
