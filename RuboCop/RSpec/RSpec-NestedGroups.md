Pattern: Too many nested example groups

Issue: -

## Description

Checks for nested example groups.

This rule is configurable using the `Max` option.

## Examples

```ruby
# bad
context 'when using some feature' do
  let(:some)    { :various }
  let(:feature) { :setup   }

  context 'when user is signed in' do  # flagged by rubocop
    let(:user) do
      UserCreate.call(user_attributes)
    end

    let(:user_attributes) do
      {
        name: 'John',
        age:  22,
        role: role
      }
    end

    context 'when user is an admin' do # flagged by rubocop
      let(:role) { 'admin' }

      it 'blah blah'
      it 'yada yada'
    end
  end
end

# better
context 'using some feature as an admin' do
  let(:some)    { :various }
  let(:feature) { :setup   }

  let(:user) do
    UserCreate.call(
      name: 'John',
      age:  22,
      role: 'admin'
    )
  end

  it 'blah blah'
  it 'yada yada'
end
```
#### configuration

```ruby
# .rubocop.yml
# RSpec/NestedGroups:
#   Max: 2

context 'when using some feature' do
  let(:some)    { :various }
  let(:feature) { :setup   }

  context 'when user is signed in' do
    let(:user) do
      UserCreate.call(user_attributes)
    end

    let(:user_attributes) do
      {
        name: 'John',
        age:  22,
        role: role
      }
    end

    context 'when user is an admin' do # flagged by rubocop
      let(:role) { 'admin' }

      it 'blah blah'
      it 'yada yada'
    end
  end
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Max | `3` | Integer

## Further Reading

* [RSpec - RSpec/NestedGroups](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecnestedgroups)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/NestedGroups](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/NestedGroups)
