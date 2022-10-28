Pattern: Redundant spec type

Issue: -

## Description

Identifies redundant spec type.

After setting up rspec-rails, you will have enabled
`config.infer_spec_type_from_file_location!` by default in
spec/rails_helper.rb. This rule works in conjunction with this config.
If you disable this config, disable this rule as well.

=== Safety

This rule is marked as unsafe because
`config.infer_spec_type_from_file_location!` may not be enabled.

## Examples

```ruby
# bad
# spec/models/user_spec.rb
RSpec.describe User, type: :model do
end

# good
# spec/models/user_spec.rb
RSpec.describe User do
end

# good
# spec/models/user_spec.rb
RSpec.describe User, type: :common do
end
```

#### `Inferences` configuration

```ruby
# .rubocop.yml
# RSpec/InferredSpecType:
#   Inferences:
#     services: service

# bad
# spec/services/user_spec.rb
RSpec.describe User, type: :service do
end

# good
# spec/services/user_spec.rb
RSpec.describe User do
end

# good
# spec/services/user_spec.rb
RSpec.describe User, type: :common do
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Inferences | `{"channels"=>"channel", "controllers"=>"controller", "features"=>"feature", "generator"=>"generator", "helpers"=>"helper", "jobs"=>"job", "mailboxes"=>"mailbox", "mailers"=>"mailer", "models"=>"model", "requests"=>"request", "integration"=>"request", "api"=>"request", "routing"=>"routing", "system"=>"system", "views"=>"view"}` | 

## Further Reading

* [RSpec - RSpec/Rails/InferredSpecType](https://docs.rubocop.org/rubocop-rspec/cops_rspec_rails.html#rspecrailsinferredspectype)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/Rails/InferredSpecType