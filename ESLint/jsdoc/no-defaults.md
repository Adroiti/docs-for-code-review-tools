Pattern: Indication of defaults on tag

Issue: -

## Description

This rule reports defaults being used on the relevant portion of `@param`
or `@default`. It also optionally reports the presence of the
square-bracketed optional arguments at all.

The rule is intended to prevent the indication of defaults on tags where
this would be redundant with ES6 default parameters (or for `@default`,
where it would be redundant with the context to which the `@default`
tag is attached).

Unless your `@default` is on a function, you will need to set `contexts`
to an appropriate context, including, if you wish, "any".


The following patterns are considered problems:

````js
/**
 * @param {number} [foo="7"]
 */
function quux (foo) {

}
// Message: Defaults are not permitted on @param.

class Test {
    /**
     * @param {number} [foo="7"]
     */
    quux (foo) {

    }
}
// Message: Defaults are not permitted on @param.

/**
 * @param {number} [foo="7"]
 */
function quux (foo) {

}
// "jsdoc/no-defaults": ["error"|"warn", {"noOptionalParamNames":true}]
// Message: Optional param names are not permitted on @param.

/**
 * @arg {number} [foo="7"]
 */
function quux (foo) {

}
// Settings: {"jsdoc":{"tagNamePreference":{"param":"arg"}}}
// Message: Defaults are not permitted on @arg.

/**
 * @param {number} [foo="7"]
 */
function quux (foo) {

}
// "jsdoc/no-defaults": ["error"|"warn", {"contexts":["any"]}]
// Message: Defaults are not permitted on @param.

/**
 * @function
 * @param {number} [foo="7"]
 */
// "jsdoc/no-defaults": ["error"|"warn", {"contexts":["any"]}]
// Message: Defaults are not permitted on @param.

/**
 * @callback
 * @param {number} [foo="7"]
 */
// "jsdoc/no-defaults": ["error"|"warn", {"contexts":["any"]}]
// Message: Defaults are not permitted on @param.

/**
 * @default {}
 */
const a = {};
// "jsdoc/no-defaults": ["error"|"warn", {"contexts":["any"]}]
// Message: Default values are not permitted on @default.

/**
 * @defaultvalue {}
 */
const a = {};
// Settings: {"jsdoc":{"tagNamePreference":{"default":"defaultvalue"}}}
// "jsdoc/no-defaults": ["error"|"warn", {"contexts":["any"]}]
// Message: Default values are not permitted on @defaultvalue.
````

The following patterns are not considered problems:

````js
/**
 * @param foo
 */
function quux (foo) {

}

/**
 * @param {number} foo
 */
function quux (foo) {

}

/**
 * @param foo
 */
// "jsdoc/no-defaults": ["error"|"warn", {"contexts":["any"]}]

/**
 * @function
 * @param {number} foo
 */

/**
 * @callback
 * @param {number} foo
 */

/**
 * @param {number} foo
 */
function quux (foo) {

}
// "jsdoc/no-defaults": ["error"|"warn", {"noOptionalParamNames":true}]

/**
 * @default
 */
const a = {};
// "jsdoc/no-defaults": ["error"|"warn", {"contexts":["any"]}]
````


## Further Reading

* [eslint-plugin-jsdoc - no-defaults](https://github.com/gajus/eslint-plugin-jsdoc/blob/main/docs/rules/no-defaults.md#readme)
