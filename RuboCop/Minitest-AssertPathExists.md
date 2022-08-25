Pattern: Missing use of `assert_path_exists`

Issue: -

## Description

Enforces the test to use `assert_path_exists` instead of using
`assert(File.exist?(path))`.

## Examples

``` ruby
# bad
assert(File.exist?(path))
assert(File.exist?(path), 'message')

# good
assert_path_exists(path)
assert_path_exists(path, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide/#assert-path-exists>