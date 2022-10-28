Pattern: Use of regex for `assert_raises`

Issue: -

## Description

Enforces checks for regular expression literals passed to `assert_raises`.

## Examples

``` ruby
# bad
assert_raises FooError, /some message/ do
  obj.occur_error
end

# good
exception = assert_raises FooError do
  obj.occur_error
end
assert_match(/some message/, exception.message)
```