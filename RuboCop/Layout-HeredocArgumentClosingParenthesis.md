Pattern: Malformed closing parenthesis for Heredoc argument

Issue: -

## Description

Checks for the placement of the closing parenthesis in a method call that passes a HEREDOC string as an argument. It should be placed at the end of the line containing the opening HEREDOC tag.

## Examples

```ruby
# bad

   foo(<<-SQL
     bar
   SQL
   )

   foo(<<-SQL, 123, <<-NOSQL,
     bar
   SQL
     baz
   NOSQL
   )

   foo(
     bar(<<-SQL
       baz
     SQL
     ),
     123,
   )

# good

   foo(<<-SQL)
     bar
   SQL

   foo(<<-SQL, 123, <<-NOSQL)
     bar
   SQL
     baz
   NOSQL

   foo(
     bar(<<-SQL),
       baz
     SQL
     123,
   )
```

## Further Reading

* [RuboCop - Layout/HeredocArgumentClosingParenthesis](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutheredocargumentclosingparenthesis)
* [https://github.com/rubocop-hq/ruby-style-guide#heredoc-argument-closing-parentheses](https://github.com/rubocop-hq/ruby-style-guide#heredoc-argument-closing-parentheses)
