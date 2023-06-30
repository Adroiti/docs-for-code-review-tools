Pattern: Missing use of shorthand from `FactoryBot::Syntax::Methods`

Issue: -

## Description

Use shorthands from `FactoryBot::Syntax::Methods` in your specs.

### Safety

The auto-correction is marked as unsafe because the cop
cannot verify whether you already include
`FactoryBot::Syntax::Methods` in your test suite.

If you're using Rails, add the following configuration to
`spec/support/factory_bot.rb` and be sure to require that file in
`rails_helper.rb`:

```ruby
RSpec.configure do |config|
  config.include FactoryBot::Syntax::Methods
end
```

If you're not using Rails:

```ruby
RSpec.configure do |config|
  config.include FactoryBot::Syntax::Methods

  config.before(:suite) do
    FactoryBot.find_definitions
  end
end
```

## Examples

```ruby
# bad
FactoryBot.create(:bar)
FactoryBot.build(:bar)
FactoryBot.attributes_for(:bar)

# good
create(:bar)
build(:bar)
attributes_for(:bar)
```

## Further Reading

* [RSpec - RSpec/FactoryBot/SyntaxMethods](https://docs.rubocop.org/rubocop-rspec/cops_rspec_factorybot.html#rspecfactorybotsyntaxmethods)