Pattern: Missing empty line after magic comment

Issue: -

## Description

Checks for a newline after the last magic comment.

## Examples

```ruby
# good
# frozen_string_literal: true


# Some documentation for Person
class Person
  # Some code
end


# bad
# frozen_string_literal: true
# Some documentation for Person
class Person
  # Some code
end
```

## Further Reading

* [RuboCop - Layout/EmptyLineAfterMagicComment](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutemptylineaftermagiccomment)
* [https://github.com/bbatsov/ruby-style-guide#separate-magic-comments-from-code](https://github.com/bbatsov/ruby-style-guide#separate-magic-comments-from-code)
