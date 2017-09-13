Pattern: Layout/LeadingCommentSpace

Issue: -

## Description

This cop checks whether comments have a leading space after the
`#` denoting the start of the comment. The leading space is not
required for some RDoc special syntax, like `#++`, `#--`,
`#:nodoc`, `=begin`- and `=end` comments, "shebang" directives,
or rackup options.

### Example

```ruby
# bad
#Some comment

# good
# Some comment
```

## Further Reading

* [RuboCop - Layout/LeadingCommentSpace](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutleadingcommentspace)
* [https://github.com/bbatsov/ruby-style-guide#hash-space](https://github.com/bbatsov/ruby-style-guide#hash-space)
