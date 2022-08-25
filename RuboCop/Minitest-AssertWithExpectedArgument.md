Pattern: Missing use of `assert_equal`

Issue: -

## Description

Tries to detect when a user accidentally used `assert` when they meant to use `assert_equal`.

## Safety

This cop is unsafe because it is not possible to determine whether the
second argument of `assert` is a message or not.

## Examples

``` ruby
# bad
assert(3, my_list.length)
assert(expected, actual)

# good
assert_equal(3, my_list.length)
assert_equal(expected, actual)
assert(foo, 'message')
```