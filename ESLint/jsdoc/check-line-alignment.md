Pattern: Invalid alignment of JSDoc block line

Issue: -

## Description

Reports invalid alignment of JSDoc block lines. This is a standard recommended to WordPress code, for example.

The following patterns are considered problems:

```js
/**
 * Function description.
 *
 * @param {string} lorem Description.
 * @param {int} sit Description multi words.
 */
const fn = ( lorem, sit ) => {}
// "jsdoc/check-line-alignment": ["error"|"warn", "always"]
// Message: Expected JSDoc block lines to be aligned.

/**
 * With tabs.
 *
 * @param {string} lorem Description.
 * @param {int} sit Description multi words.
 */
    const fn = ( lorem, sit ) => {}
// "jsdoc/check-line-alignment": ["error"|"warn", "always"]
// Message: Expected JSDoc block lines to be aligned.

/**
 * Function description.
 *
 * @param {string} lorem - Description.
 * @param {int} sit - Description multi words.
 */
const fn = ( lorem, sit ) => {}
// "jsdoc/check-line-alignment": ["error"|"warn", "always"]
// Message: Expected JSDoc block lines to be aligned.
```

The following patterns are not considered problems:

```js
/**
 * Function description.
 *
 * @param {string} lorem Description.
 * @param {int}    sit   Description multi words.
 */
const fn = ( lorem, sit ) => {}
// "jsdoc/check-line-alignment": ["error"|"warn", "always"]

/**
 * With tabs.
 *
 * @param {string} lorem Description.
 * @param {int}    sit   Description multi words.
 */
    const fn = ( lorem, sit ) => {}
// "jsdoc/check-line-alignment": ["error"|"warn", "always"]

/**
 * Function description.
 *
 * @param {string} lorem - Description.
 * @param {int}    sit   - Description multi words.
 */
const fn = ( lorem, sit ) => {}
// "jsdoc/check-line-alignment": ["error"|"warn", "always"]
```

## Further Reading

* [eslint-plugin-jsdoc - check-line-alignment](https://github.com/gajus/eslint-plugin-jsdoc#eslint-plugin-jsdoc-rules-check-line-alignment)