Pattern: Use of newline after description

Issue: -

## Description

Enforces a consistent padding of the block description.

<a name="eslint-plugin-jsdoc-rules-newline-after-description-options-11"></a>
#### Options

This rule allows one optional string argument. If it is `"always"` then a problem is raised when there is no newline after the description. If it is `"never"` then a problem is raised when there is a newline after the description. The default value is `"always"`.

|||
|---|---|
|Context|everywhere|
|Options|(a string matching `"always"|"never"`)|
|Tags|N/A (doc block)|

The following patterns are considered problems:

````js
/**
 * Foo.
 *
 * Foo.
 * @foo
 */
function quux () {

}
// Options: ["always"]
// Message: There must be a newline after the description of the JSDoc block.

/**
 * Foo.
 * @foo
 *
 * Foo.
 */
function quux () {

}
// Options: ["always"]
// Message: There must be a newline after the description of the JSDoc block.

/**
 * Foo.
 *
 * Foo.
 * @foo
 */
function quux () {

}
// Message: There must be a newline after the description of the JSDoc block.

/**
 * Bar.
 *
 * Bar.
 *
 * @bar
 */
function quux () {

}
// Options: ["never"]
// Message: There must be no newline after the description of the JSDoc block.

/**
 * Bar.
 *
 * @bar
 *
 * Bar.
 */
function quux () {

}
// Options: ["never"]
// Message: There must be no newline after the description of the JSDoc block.


         /**
          * Bar.
          *
          * Bar.
          *
          * @bar
          */
         function quux () {

         }
// Options: ["never"]
// Message: There must be no newline after the description of the JSDoc block.

/**
 * A.
 *
 * @typedef {object} A
 * @prop {boolean} a A.
 */
// Options: ["never"]
// Message: There must be no newline after the description of the JSDoc block.

/**
 * A.
 * @typedef {object} A
 * @prop {boolean} a A.
 */
// Options: ["always"]
// Message: There must be a newline after the description of the JSDoc block.


     /**
      * Service for fetching symbols.
      * @param {object} $http - Injected http helper.
      * @param {object} $q - Injected Promise api helper.
      * @param {object} $location - Injected window location object.
      * @param {object} REPORT_DIALOG_CONSTANTS - Injected handle.
      */
// Message: There must be a newline after the description of the JSDoc block.
````

The following patterns are not considered problems:

````js
/**
 * Foo.
 */
function quux () {

}
// Options: ["always"]

/**
 * Bar.
 */
function quux () {

}
// Options: ["never"]

/**
 * Foo.
 *
 * @foo
 */
function quux () {

}
// Options: ["always"]

/**
 * Bar.
 * @bar
 */
function quux () {

}
// Options: ["never"]


     /**
      * @foo
      * Test 
      * abc 
      * @bar 
      */


     /**
      * 
      * @foo
      * Test 
      * abc 
      * @bar 
      */

/***
 *
 */
function quux () {

}
// Options: ["always"]

/**
 * Parses query string to object containing URL parameters
 * 
 * @param queryString
 * Input string
 * 
 * @returns
 * Object containing URL parameters
 */
export function parseQueryString(queryString: string): { [key: string]: string } {    // <-- Line 10 that fails

}
````


<a name="eslint-plugin-jsdoc-rules-no-types"></a>

## Further Reading

* [eslint-plugin-jsdoc - newline-after-description](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#newline-after-description)
