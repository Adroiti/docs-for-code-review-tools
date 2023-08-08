Pattern: Invalid Heredoc method call position

Issue: -

## Description

Checks for the ordering of a method call where the receiver of the call is a HEREDOC.

## Examples

```ruby
# bad

   <<-SQL
     bar
   SQL
   .strip_indent

   <<-SQL
     bar
   SQL
   .strip_indent
   .trim

# good

   <<-SQL.strip_indent
     bar
   SQL

   <<-SQL.strip_indent.trim
     bar
   SQL
```

## Further Reading

* [RuboCop - Lint/HeredocMethodCallPosition](https://docs.rubocop.org/rubocop/cops_lint.html#lintheredocmethodcallposition)
* [https://github.com/rubocop-hq/ruby-style-guide#heredoc-method-calls](https://github.com/rubocop-hq/ruby-style-guide#heredoc-method-calls)
