Pattern: Space after `,`

Issue: -

## Description

Checks for comma (`,`) not followed by some kind of space.

## Examples

```ruby
# bad
1,2
{ foo:bar,}

# good
1, 2
{ foo:bar, }
```

## Further Reading

* [RuboCop - Layout/SpaceAfterComma](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspaceaftercomma)
* [https://github.com/bbatsov/ruby-style-guide#spaces-operators](https://github.com/bbatsov/ruby-style-guide#spaces-operators)
