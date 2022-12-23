Pattern: Missing use of `Array#intersect?`

Issue: -

## Description

In Ruby 3.1, `Array#intersect?` has been added.

This rule identifies places where `(array1 & array2).any?`
can be replaced by `array1.intersect?(array2)`.

The `array1.intersect?(array2)` method is faster than
`(array1 & array2).any?` and is more readable.

## Examples

```ruby
# bad
(array1 & array2).any?
(array1 & array2).empty?

# good
array1.intersect?(array2)
!array1.intersect?(array2)
```

#### AllCops:ActiveSupportExtensionsEnabled: false (default)

```ruby
# good
(array1 & array2).present?
(array1 & array2).blank?
```

#### AllCops:ActiveSupportExtensionsEnabled: true

```ruby
# bad
(array1 & array2).present?
(array1 & array2).blank?

# good
array1.intersect?(array2)
!array1.intersect?(array2)
```

## Further Reading

* [RuboCop - Style/ArrayIntersect](https://docs.rubocop.org/rubocop/cops_style.html#stylearrayintersect)
