Pattern: Use of `method_missing` without `super`

Issue: -

## Description

This rule checks for the presence of `method_missing` without falling back on `super`.

## Examples

```ruby
#bad
def method_missing(name, *args)
  # ...
end

#good

def method_missing(name, *args)
  # ...
  super
end
```

## Further Reading

* [RuboCop - Style/MethodMissingSuper](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemethodmissingsuper)
* [GitHub - rubocop-hq/ruby-style-guide](https://github.com/rubocop-hq/ruby-style-guide#no-method-missing)
