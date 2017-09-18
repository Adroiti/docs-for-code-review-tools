Pattern: Redundant `self`

Issue: -

## Description

This rule checks for redundant uses of `self`.

`self` is only needed when sending a message to same object with zero arguments in presence of a method name clash with an argument or a local   variable.

Note, with using explicit self you can only send messages with public or protected scope, you cannot send private messages this way.

## Examples

```ruby
# bad
def ready?
  if self.last_reviewed_at > self.last_updated_at
    self.worker.update(self.content, self.options)
    self.status = :in_progress
  end
  self.status == :verified
end

# good
def ready?
  if last_reviewed_at > last_updated_at
    worker.update(content, options)
    self.status = :in_progress
  end
  status == :verified
end
```

## Further Reading

* [RuboCop - Style/RedundantSelf](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantself)
* [https://github.com/bbatsov/ruby-style-guide#no-self-unless-required](https://github.com/bbatsov/ruby-style-guide#no-self-unless-required)
