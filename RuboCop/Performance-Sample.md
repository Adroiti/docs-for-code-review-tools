Pattern: Missing use of `sample`

Issue: -

## Description

This rule is used to identify usages of `shuffle.first`, `shuffle.last`
and `shuffle[]` and change them to use `sample` instead.

## Examples

```ruby
# bad
[1, 2, 3].shuffle.first
[1, 2, 3].shuffle.first(2)
[1, 2, 3].shuffle.last
[1, 2, 3].shuffle[2]
[1, 2, 3].shuffle[0, 2]    # sample(2) will do the same
[1, 2, 3].shuffle[0..2]    # sample(3) will do the same
[1, 2, 3].shuffle(random: Random.new).first

# good
[1, 2, 3].shuffle
[1, 2, 3].sample
[1, 2, 3].sample(3)
[1, 2, 3].shuffle[1, 3]    # sample(3) might return a longer Array
[1, 2, 3].shuffle[1..3]    # sample(3) might return a longer Array
[1, 2, 3].shuffle[foo, bar]
[1, 2, 3].shuffle(random: Random.new)
```

## Further Reading

* [RuboCop - Performance/Sample](https://docs.rubocop.org/rubocop/cops_style.html#stylesample)
* [https://github.com/JuanitoFatas/fast-ruby#arrayshufflefirst-vs-arraysample-code](https://github.com/JuanitoFatas/fast-ruby#arrayshufflefirst-vs-arraysample-code)
