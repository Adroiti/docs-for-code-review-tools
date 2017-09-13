Pattern: Layout/SpaceAfterComma

Issue: -

## Description

Checks for comma (,) not followed by some kind of space.

### Example

```ruby
# bad
1,2
{ foo:bar,}

# good
1, 2
{ foo:bar, }
```

## Further Reading

* [RuboCop - Layout/SpaceAfterComma](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspaceaftercomma)
* [https://github.com/bbatsov/ruby-style-guide#spaces-operators](https://github.com/bbatsov/ruby-style-guide#spaces-operators)
