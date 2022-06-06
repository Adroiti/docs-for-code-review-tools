Pattern: Use of `to change.by(0)`

Issue: -

## Description

Prefer negated matchers over `to change.by(0)`.

## Examples

```ruby
# bad
expect { run }.to change(Foo, :bar).by(0)
expect { run }.to change { Foo.bar }.by(0)
expect { run }
  .to change(Foo, :bar).by(0)
  .and change(Foo, :baz).by(0)
expect { run }
  .to change { Foo.bar }.by(0)
  .and change { Foo.baz }.by(0)

# good
expect { run }.not_to change(Foo, :bar)
expect { run }.not_to change { Foo.bar }
expect { run }
  .to not_change(Foo, :bar)
  .and not_change(Foo, :baz)
expect { run }
  .to not_change { Foo.bar }
  .and not_change { Foo.baz }
```

## Further Reading

* [RSpec - RSpec/ChangeByZero](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecchangebyzero)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ChangeByZero