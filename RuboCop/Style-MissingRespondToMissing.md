Pattern: Missing use of `respond_to_missing?`

Issue: -

## Description

This rule checks for the presence of `method_missing` without also defining `respond_to_missing?`.

## Examples

```ruby
#bad
def method_missing(name, *args)
  # ...
end

#good
def respond_to_missing?(name, include_private)
  # ...
end

def method_missing(name, *args)
  # ...
end
```

## Further Reading

* [RuboCop - Style/MissingRespondToMissing](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemissingrespondtomissing)
* [GitHub - rubocop-hq/ruby-style-guide](https://github.com/rubocop-hq/ruby-style-guide#no-method-missing)
