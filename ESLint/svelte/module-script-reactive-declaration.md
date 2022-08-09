Pattern: Malformed script reactive declaration

Issue: -

## Description

Rule #1: `$:` has no effect in a module script.
Rule #2: `${names.map(name => "${name}").join(', ')} ${names.length > 1 ? 'are' : 'is'}` declared in a module script and will not be reactive.