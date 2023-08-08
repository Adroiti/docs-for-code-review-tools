Pattern: Use of `#to_json` without optional argument

Issue: -

## Description

When overriding `#to_json`, callers may invoke JSON generation via `JSON.generate(your_obj)`. Since `JSON#generate` allows for an optional argument, your method should too.

### Examples

```ruby
# bad
def to_json
end

# good
def to_json(_opts)
end
```

## Further Reading

* [RuboCop - Lint/ToJSON](https://docs.rubocop.org/rubocop/cops_lint.html#linttojson)
