Pattern: Redundant `Array` constructor

Issue: -

## Description

Checks for the instantiation of array using redundant `Array` constructor. Autocorrect replaces to array literal which is the simplest and fastest.

## Examples

```ruby
# bad
Array.new([])
Array[]
Array([])
Array.new(['foo', 'foo', 'foo'])
Array['foo', 'foo', 'foo']
Array(['foo', 'foo', 'foo'])

# good
[]
['foo', 'foo', 'foo']
Array.new(3, 'foo')
Array.new(3) { 'foo' }
```

## Further Reading

* [RuboCop - Style/RedundantArrayConstructor](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantarrayconstructor)
