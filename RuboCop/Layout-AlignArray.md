Pattern: Layout/AlignArray

Issue: -

## Description

Here we check if the elements of a multi-line array literal are
aligned.

### Example

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

* [RuboCop - Layout/AlignArray](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutalignarray)
* [https://github.com/bbatsov/ruby-style-guide#align-multiline-arrays](https://github.com/bbatsov/ruby-style-guide#align-multiline-arrays)
