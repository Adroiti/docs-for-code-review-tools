Pattern: Missing `description` for `@property`

Issue: -

## Description

Requires that each `@property` tag has a `description` value.

|||
|---|---|
|Context|everywhere|
|Tags|N/A|

The following patterns are considered problems:

````js
/**
 * @typedef {SomeType} SomeTypedef
 * @property foo
 */
// Message: Missing JSDoc @property "foo" description.

/**
 * @typedef {SomeType} SomeTypedef
 * @prop foo
 */
// Settings: {"jsdoc":{"tagNamePreference":{"property":"prop"}}}
// Message: Missing JSDoc @prop "foo" description.

/**
 * @typedef {SomeType} SomeTypedef
 * @property foo
 */
// Settings: {"jsdoc":{"tagNamePreference":{"property":false}}}
// Message: Unexpected tag `@property`
````

The following patterns are not considered problems:

````js
/**
 * @typedef {SomeType} SomeTypedef
 */

/**
 * @typedef {SomeType} SomeTypedef
 * @property foo Foo.
 */

/**
 * @namespace {SomeType} SomeName
 * @property foo Foo.
 */

/**
 * @class
 * @property foo Foo.
 */
````


<a name="eslint-plugin-jsdoc-rules-require-property-name"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-property-description](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-property-description)
