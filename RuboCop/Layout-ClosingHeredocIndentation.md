Pattern: Malformed closing heredoc indentation

Issue: -

## Description

Checks the indentation of here document closings.

## Examples

```ruby
# bad
class Foo
  def bar
    <<~SQL
      'Hi'
  SQL
  end
end

# good
class Foo
  def bar
    <<~SQL
      'Hi'
    SQL
  end
end

# bad

# heredoc contents is before closing heredoc.
foo arg,
    <<~EOS
  Hi
    EOS

# good
foo arg,
    <<~EOS
  Hi
EOS

# good
foo arg,
    <<~EOS
      Hi
    EOS
```

## Further Reading

* [RuboCop - Layout/ClosingHeredocIndentation](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutclosingheredocindentation)
