Pattern: Missing use of `assert_output`

Issue: -

## Description

Checks for opportunities to use `assert_output`.

## Examples

``` ruby
# bad
$stdout = StringIO.new
puts object.method
$stdout.rewind
assert_match expected, $stdout.read

# good
assert_output(expected) { puts object.method }
```

## Further Reading

- <https://minitest.rubystyle.guide/#assert-output>