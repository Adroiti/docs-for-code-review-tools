Pattern: Missing `@property` name

Issue: -

## Description

Requires that all function `@property` tags have names.

|||
|---|---|
|Context|everywhere|
|Tags|N/A|

The following patterns are considered problems:

````js
/**
 * @typedef {SomeType} SomeTypedef
 * @property
 */
// Message: There must be an identifier after @property type.

/**
 * @typedef {SomeType} SomeTypedef
 * @property {string}
 */
// Message: There must be an identifier after @property tag.

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
 * @property foo
 */

/**
 * @typedef {SomeType} SomeTypedef
 * @property {string} foo
 */

/**
 * @namespace {SomeType} SomeName
 * @property {string} foo
 */

/**
 * @class
 * @property {string} foo
 */
````


<a name="eslint-plugin-jsdoc-rules-require-property-type"></a>

## Further Reading

* [eslint-plugin-jsdoc - require-property-name](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#require-property-name)
