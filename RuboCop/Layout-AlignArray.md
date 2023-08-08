Pattern: Misaligned element of multi-line array

Issue: -

## Description

This rule checks if the elements of a multi-line array literal are aligned.

## Examples

```ruby
# bad
a = [1, 2, 3,
  4, 5, 6]
array = ['run',
     'forrest',
     'run']

# good
a = [1, 2, 3,
     4, 5, 6]
a = ['run',
     'forrest',
     'run']
```

## Further Reading

* [RuboCop - Layout/AlignArray](https://docs.rubocop.org/rubocop/cops_layout.html#layoutalignarray)
* [https://github.com/bbatsov/ruby-style-guide#align-multiline-arrays](https://github.com/bbatsov/ruby-style-guide#align-multiline-arrays)
