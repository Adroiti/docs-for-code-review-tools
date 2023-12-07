Pattern: Use of `arr[0]`/`arr[-1]`

Issue: -

## Description

Identifies usages of `arr[0]` and `arr[-1]` and suggests to change them to use `arr.first` and `arr.instead`.

## Examples

```ruby
# bad
arr[0]
arr[-1]

# good
arr.first
arr.last
arr[0] = 2
arr[0][-2]
```

## Further Reading

* [RuboCop - ArrayFirstLast](https://docs.rubocop.org/rubocop/cops_style.html#stylearrayfirstlast)