Pattern: Malformed tag line

Issue: -

## Description

Enforces lines (or no lines) between tags.

The following patterns are considered problems:

````js
/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "always"]
// Message: Expected 1 line between tags but found 0

/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "always",{"count":2}]
// Message: Expected 2 lines between tags but found 0

/**
 * Some description
 * @param {string} a
 *
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "always",{"count":2}]
// Message: Expected 2 lines between tags but found 1

/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "always",{"noEndLines":true}]
// Message: Expected 1 line between tags but found 0

/**
 * Some description
 * @param {string} a
 *
 * @param {number} b
 *
 */
// "jsdoc/tag-lines": ["error"|"warn", "never"]
// Message: Expected no lines between tags

/**
 * Some description
 * @param {string} a
 *
 * @param {number} b
 *
 */
// Message: Expected no lines between tags

/**
 * Some description
 * @param {string} a
 *
 * @param {number} b
 * @param {number} c
 */
// "jsdoc/tag-lines": ["error"|"warn", "always"]
// Message: Expected 1 line between tags but found 0

/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"tags":{"param":{"lines":"always"}}}]
// Message: Expected 1 line between tags but found 0

/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"tags":{"param":{"lines":"always"}}}]
// Message: Expected 1 line between tags but found 0

/**
 * Some description
 * @param {string} a
 * @param {number} b
 *
 */
// "jsdoc/tag-lines": ["error"|"warn", "always",{"tags":{"param":{"lines":"never"}}}]
// Message: Expected no lines between tags

/**
 * Some description
 * @param {string} a
 *
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"count":2,"tags":{"param":{"lines":"always"}}}]
// Message: Expected 2 lines between tags but found 1

/**
 * Some description
 * @param {string} a
 *
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"count":5,"tags":{"param":{"count":2,"lines":"always"}}}]
// Message: Expected 2 lines between tags but found 1

/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "always",{"tags":{"anotherTag":{"lines":"never"}}}]
// Message: Expected 1 line between tags but found 0

/**
 * Some description
 * @param {string} A broken up
 *
 * tag description.
 * @param {number} b
 *
 */
// "jsdoc/tag-lines": ["error"|"warn", "always"]
// Message: Expected 1 line between tags but found 0

/**
 * Some description
 * @param {number} b
 *
 * @returns {string} A broken up
 *
 * tag description.
 */
// "jsdoc/tag-lines": ["error"|"warn", "always"]
// Message: Expected 1 line between tags but found 0
````

The following patterns are not considered problems:

````js
/**
 * Some description
 * @param {string} a
 * @param {number} b
 */

/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "never"]

/**
 * @param {string} a
 *
 * @param {string} a
 */
// "jsdoc/tag-lines": ["error"|"warn", "always",{"noEndLines":true}]

/**
 * @param {string} a
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"noEndLines":true}]

/** @param {number} b */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"noEndLines":true}]

/**
 * Some description
 * @param {string} a
 *
 * @param {number} b
 *
 */
// "jsdoc/tag-lines": ["error"|"warn", "always"]

/**
 * Some description
 * @param {string} a
 *
 *
 * @param {number} b
 *
 *
 */
// "jsdoc/tag-lines": ["error"|"warn", "always",{"count":2}]

/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"tags":{"param":{"lines":"any"}}}]

/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "always",{"tags":{"param":{"lines":"never"}}}]

/**
 * Some description
 * @param {number} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"tags":{"param":{"lines":"any"}}}]

/**
 * Some description
 * @param {number} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"tags":{"param":{"lines":"never"}}}]

/**
 * Some description
 * @param {string} a
 *
 *
 * @param {number} b
 *
 *
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"count":5,"tags":{"param":{"count":2,"lines":"always"}}}]

/**
 * Some description
 * @param {string} a
 * @param {number} b
 */
// "jsdoc/tag-lines": ["error"|"warn", "never",{"tags":{"anotherTag":{"lines":"always"}}}]

/**
 * Some description
 * @param {string} a
 *
 * This is still part of `@param`.
 * @returns {SomeType} An extended
 * description.
 */
// "jsdoc/tag-lines": ["error"|"warn", "never"]

/**
 * Some description
 * @param {string} a
 * @returns {SomeType} An extended
 * description.
 *
 * This is still part of `@returns`.
 */
// "jsdoc/tag-lines": ["error"|"warn", "never"]

/**
 * Some description
 * @param {string} a
 *
 * This is still part of `@param`.
 *
 * @returns {SomeType} An extended
 * description.
 *
 */
// "jsdoc/tag-lines": ["error"|"warn", "always"]

/**
 * Some description
 * @param {string} a
 *
 * @returns {SomeType} An extended
 * description.
 *
 * This is still part of `@returns`.
 *
 */
// "jsdoc/tag-lines": ["error"|"warn", "always"]
````

## Further Reading

* [eslint-plugin-jsdoc - tag-lines](https://github.com/gajus/eslint-plugin-jsdoc#tag-lines)
