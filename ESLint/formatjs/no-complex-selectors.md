Pattern: Use of complex selector

Issue: -

## Description

Make sure a sentence is not too complex. Complexity is determined by how many strings are produced when we try to flatten the sentence given its selectors. For example:

```json
I have {count, plural, one{a dog} other{many dogs}}
```

has the complexity of 2 because flattening the plural selector results in 2 sentences: I have a dog & I have many dogs. Default complexity limit is 20.

## Further Reading

* [formatjs - no-complex-selectors](https://formatjs.io/docs/tooling/linter/#no-complex-selectors)