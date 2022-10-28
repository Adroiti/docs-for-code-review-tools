Pattern: Duplicate magic comment

Issue: -

## Description

Checks for duplicated magic comments.

## Examples

```ruby
# bad

# encoding: ascii
# encoding: ascii

# good

# encoding: ascii

# bad

# frozen_string_literal: true
# frozen_string_literal: true

# good

# frozen_string_literal: true
```

## Further Reading

* [RuboCop - Lint/DuplicateMagicComment](https://docs.rubocop.org/rubocop/cops_lint.html#lintduplicatemagiccomment)
