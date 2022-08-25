Pattern: Missing use of `refute_path_exists`

Issue: -

## Description

Enforces the test to use `refute_path_exists` instead of using
`refute(File.exist?(path))`.

## Examples

``` ruby
# bad
refute(File.exist?(path))
refute(File.exist?(path), 'message')

# good
refute_path_exists(path)
refute_path_exists(path, 'message')
```

## Further Reading

- <https://minitest.rubystyle.guide/#refute-path-exists>