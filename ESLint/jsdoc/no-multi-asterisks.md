Pattern: Use of multi asterisks

Issue: -

## Description

Prevents use of multiple asterisks at the beginning of lines.

Note that if you wish to prevent multiple asterisks at the very beginning of the jsdoc block, you should use `no-bad-blocks` (as that is not proper jsdoc and that rule is for catching blocks which only seem like jsdoc).

The following patterns are considered problems:

````js
/**
 *
 **
 */
// Message: Should be no multiple asterisks on middle lines.

/**
 *
 **
 */
// "jsdoc/no-multi-asterisks": ["error"|"warn", {"preventAtMiddleLines":true}]
// Message: Should be no multiple asterisks on middle lines.

/**
 *
 **
 */
// "jsdoc/no-multi-asterisks": ["error"|"warn", {"preventAtEnd":false}]
// Message: Should be no multiple asterisks on middle lines.

/**
 * With a description
 * @tag {SomeType} and a tag with details
 **
 */
// Message: Should be no multiple asterisks on middle lines.

/**
 **
 *
 */
// Message: Should be no multiple asterisks on middle lines.

/**
 * Desc.
 *
 **/
// Message: Should be no multiple asterisks on end lines.

/**
 * Desc.
 *
 **/
// "jsdoc/no-multi-asterisks": ["error"|"warn", {"preventAtEnd":true}]
// Message: Should be no multiple asterisks on end lines.

/**
 * Desc.
 *
 abc * **/
// "jsdoc/no-multi-asterisks": ["error"|"warn", {"preventAtEnd":true}]
// Message: Should be no multiple asterisks on end lines.

/**
 * Desc.
 *
 **/
// "jsdoc/no-multi-asterisks": ["error"|"warn", {"preventAtMiddleLines":false}]
// Message: Should be no multiple asterisks on end lines.

/** Desc. **/
// Message: Should be no multiple asterisks on end lines.

/** @someTag name desc. **/
// Message: Should be no multiple asterisks on end lines.

/** abc * */
// Message: Should be no multiple asterisks on end lines.

/**
 * Preserve user's whitespace when fixing (though one may also
 *   use an align rule)
 *
 * */
// "jsdoc/no-multi-asterisks": ["error"|"warn", {"preventAtEnd":true}]
// Message: Should be no multiple asterisks on end lines.
````

The following patterns are not considered problems:

````js
/**
 *
 * Desc. ***
 */

/**
 * Desc. ***
 *
 */

/**
 * Desc.
 *
 * sth */

/**
 **
 *
 */
// "jsdoc/no-multi-asterisks": ["error"|"warn", {"preventAtMiddleLines":false}]

/**
 *
 *
 **/
// "jsdoc/no-multi-asterisks": ["error"|"warn", {"preventAtEnd":false}]

/**
 * With a desc.
 * and ***
 */

/**
 * and ***
 * With a desc.
 */

/**
 * With a desc.
 * With a desc.
 * Desc. */

/**
 * With a description
 * @tag {SomeType} and a tag with details
 *
 */

/** abc */
function foo() {
    //
}

/** foo */
function foo(): void {
    //
}

/** @aTag abc */
function foo() {
    //
}
````

## Further Reading

* [eslint-plugin-jsdoc - no-multi-asterisks](https://github.com/gajus/eslint-plugin-jsdoc#no-multi-asterisks)
