Pattern: Use of indexed `let`

Issue: -

## Description

Do not set up test data using indexes (e.g., `item_1`, `item_2`).

It makes reading the test harder because it's not clear what exactly
is tested by this particular example.

## Examples

#### `Max: 1 (default)`

```ruby
# bad
let(:item_1) { create(:item) }
let(:item_2) { create(:item) }

let(:item1) { create(:item) }
let(:item2) { create(:item) }

# good

let(:visible_item) { create(:item, visible: true) }
let(:invisible_item) { create(:item, visible: false) }
```

#### `Max: 2`

```ruby
# bad
let(:item_1) { create(:item) }
let(:item_2) { create(:item) }
let(:item_3) { create(:item) }

# good
let(:item_1) { create(:item) }
let(:item_2) { create(:item) }
```

## Further Reading

* [RSpec - RSpec/IndexedLet](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecindexedlet)