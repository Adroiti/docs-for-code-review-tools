Pattern: Use of problematic term

Issue: -

## Description

This rule recommends the use of inclusive language instead of problematic terms. The cop can check the following locations for offenses: - identifiers - constants - variables - strings - symbols - comments - file paths Each of these locations can be individually enabled/disabled via configuration, for example CheckIdentifiers = true/false.

Flagged terms are configurable. For each flagged term an optional Regex can be specified to identify offenses. Suggestions for replacing a flagged term can be configured and will be displayed as part of the offense message. An AllowedRegex can be specified for a flagged term to exempt allowed uses of the term.


## Examples

FlaggedTerms: { whitelist: { Suggestions: ['allowlist'] } }

```ruby
# Suggest replacing identifier whitelist with allowlist

# bad
whitelist_users = %w(user1 user1)

# good
allowlist_users = %w(user1 user2)
```

## Further Reading

* [RuboCop - Naming/InclusiveLanguage](https://docs.rubocop.org/rubocop/cops_naming.html#naminginclusivelanguage)