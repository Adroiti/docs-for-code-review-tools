Pattern: Mismatched Phrase bundle and translation keys

Issue: -

## Description

Prefer matching Phrase Bundle and translation call keys.

## Examples

```ruby
# bad
def phrases
  {
    "shortened_key" => t(
      "my_real_translation_key",
      default: 'Does not matter',
    ),
  }
end

# good
def phrases
  {
    "my_real_translation_key" => t(
      "my_real_translation_key",
      default: 'Does not matter',
    ),
  }
end
```

## Further Reading

* [RuboCop - Airbnb/PhraseBundleKeys](https://github.com/airbnb/ruby/blob/master/rubocop-airbnb/lib/rubocop/cop/airbnb/phrase_bundle_keys.rb)
