Pattern: Missing use of arrow function

Issue: -

## Description

Rule to prefer arrow functions. By default, it allows usage of `function` as a member of an Object's prototype, but this can be changed with the property `disallowPrototype`. Alternatively, with the `singleReturnOnly` option, this plugin only reports functions where converting to an arrow function would dramatically simplify the code.

## Configuration
* `disallowPrototype`: If set to true, the plugin will warn if `function` is used anytime. Otherwise, the plugin allows usage of `function` if it is a member of an Object's prototype.
* `singleReturnOnly`: If set to true, the plugin will only warn for `function` declarations which *only* contain a return statement. These often look much better when declared as arrow functions without braces. Works well in conjunction with ESLint's built-in [arrow-body-style](http://eslint.org/docs/rules/arrow-body-style) set to `as-needed`.
* `classPropertiesAllowed`: (Only takes effect if `singleReturnOnly` is enabled) If set to true, the plugin will warn about functions which could be replaced with arrow functions defined as [class instance fields](https://github.com/jeffmo/es-class-static-properties-and-fields). Enable if you're using Babel's [transform-class-properties](https://babeljs.io/docs/plugins/transform-class-properties/) plugin.