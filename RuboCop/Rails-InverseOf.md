Pattern: Missing use of `:inverse_of`

Issue: -

## Description

This rule looks for has_(one|many) and belongs_to associations where
ActiveRecord can't automatically determine the inverse association
because of a scope or the options used. This can result in unnecessary
queries in some circumstances. `:inverse_of` must be manually specified
for associations to work in both ways, or set to `false` or `nil`
to opt-out.

## Examples

```ruby
# good
class Blog < ApplicationRecord
  has_many :posts
end

class Post < ApplicationRecord
  belongs_to :blog
end
```
```ruby
# bad
class Blog < ApplicationRecord
  has_many :posts, -> { order(published_at: :desc) }
end

class Post < ApplicationRecord
  belongs_to :blog
end

# good
class Blog < ApplicationRecord
  has_many(:posts,
    -> { order(published_at: :desc) },
    inverse_of: :blog
  )
end

class Post < ApplicationRecord
  belongs_to :blog
end

# good
class Blog < ApplicationRecord
  with_options inverse_of: :blog do
    has_many :posts, -> { order(published_at: :desc) }
  end
end

class Post < ApplicationRecord
  belongs_to :blog
end

# good
# When you don't want to use the inverse association.
class Blog < ApplicationRecord
  has_many(:posts,
    -> { order(published_at: :desc) },
    inverse_of: false
  )
end

# good
# You can also opt-out with specifying `inverse_of: nil`.
class Blog < ApplicationRecord
  has_many(:posts,
    -> { order(published_at: :desc) },
    inverse_of: nil
  )
end
```
```ruby
# bad
class Picture < ApplicationRecord
  belongs_to :imageable, polymorphic: true
end

class Employee < ApplicationRecord
  has_many :pictures, as: :imageable
end

class Product < ApplicationRecord
  has_many :pictures, as: :imageable
end

# good
class Picture < ApplicationRecord
  belongs_to :imageable, polymorphic: true
end

class Employee < ApplicationRecord
  has_many :pictures, as: :imageable, inverse_of: :imageable
end

class Product < ApplicationRecord
  has_many :pictures, as: :imageable, inverse_of: :imageable
end
```
```ruby
# bad
# However, RuboCop can not detect this pattern...
class Physician < ApplicationRecord
  has_many :appointments
  has_many :patients, through: :appointments
end

class Appointment < ApplicationRecord
  belongs_to :physician
  belongs_to :patient
end

class Patient < ApplicationRecord
  has_many :appointments
  has_many :physicians, through: :appointments
end

# good
class Physician < ApplicationRecord
  has_many :appointments
  has_many :patients, through: :appointments
end

class Appointment < ApplicationRecord
  belongs_to :physician, inverse_of: :appointments
  belongs_to :patient, inverse_of: :appointments
end

class Patient < ApplicationRecord
  has_many :appointments
  has_many :physicians, through: :appointments
end
```

## Default configuration

Attribute | Value
--- | ---
Include | `app/models/**/*.rb`

## Further Reading

* [RuboCop - Rails/InverseOf](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsinverseof)
