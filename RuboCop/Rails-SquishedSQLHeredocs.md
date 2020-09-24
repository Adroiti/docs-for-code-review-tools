Pattern: Missing use of `.squish` for SQL heredoc

Issue: -

## Description

Checks SQL heredocs to use `.squish`.

## Examples

```ruby
# bad
<<-SQL
  SELECT * FROM posts;
SQL

<<-SQL
  SELECT * FROM posts
    WHERE id = 1
SQL

execute(<<~SQL, "Post Load")
  SELECT * FROM posts
    WHERE post_id = 1
SQL

# good
<<-SQL.squish
  SELECT * FROM posts;
SQL

<<~SQL.squish
  SELECT * FROM table
    WHERE id = 1
SQL

execute(<<~SQL.squish, "Post Load")
  SELECT * FROM posts
    WHERE post_id = 1
SQL
```

## Further Reading

* [RuboCop - Rails/SquishedSQLHeredocs](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railssquishedsqlheredocs)
