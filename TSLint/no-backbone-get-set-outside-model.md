Pattern: Backbone `get()`/`set()` called outside of owning model

Issue: -

## Description

Avoid using `model.get('x')` and `model.set('x', value)` Backbone
accessors outside of the owning model. This breaks type safety and you
should define getters and setters for your attributes instead.

## Further Reading

* [TSLint - no-backbone-get-set-outside-model](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)