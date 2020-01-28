Pattern: Invalid JSDoc property name

Issue: -

## Description

Ensures that property names in JSDoc are not duplicated on the same block
and that nested properties have defined roots.

<a name="eslint-plugin-jsdoc-rules-check-property-names-options-4"></a>
#### Options

|||
|---|---|
|Context|Everywhere|
|Tags|`property`|

The following patterns are considered problems:

````js
/**
 * @typedef (SomeType) SomeTypedef
 * @property Foo.Bar
 */
// Message: @property path declaration ("Foo.Bar") appears before any real property.

/**
 * @typedef (SomeType) SomeTypedef
 * @property foo
 * @property Foo.Bar
 */
// Message: @property path declaration ("Foo.Bar") root node name ("Foo") does not match previous real property name ("foo").

/**
 * Assign the project to a list of employees.
 * @typedef (SomeType) SomeTypedef
 * @property {string} employees[].name - The name of an employee.
 * @property {string} employees[].department - The employee's department.
 */
// Message: @property path declaration ("employees[].name") appears before any real property.

/**
 * Assign the project to a list of employees.
 * @typedef (SomeType) SomeTypedef
 * @property {string} employees[].name - The name of an employee.
 * @property {string} employees[].name - The employee's department.
 */
// Message: Duplicate @property "employees[].name"

/**
 * @typedef (SomeType) SomeTypedef
 * @property foo
 * @property foo
 */
// Message: Duplicate @property "foo"

/**
 * @typedef (SomeType) SomeTypedef
 * @property cfg
 * @property cfg.foo
 * @property cfg.foo
 */
function quux ({foo, bar}) {

}
// Message: Duplicate @property "cfg.foo"

/**
 * @typedef (SomeType) SomeTypedef
 * @property cfg
 * @property cfg.foo
 * @property [cfg.foo]
 * @property baz
 */
function quux ({foo, bar}, baz) {

}
// Message: Duplicate @property "cfg.foo"

/**
 * @typedef (SomeType) SomeTypedef
 * @property cfg
 * @property cfg.foo
 * @property [cfg.foo="with a default"]
 * @property baz
 */
function quux ({foo, bar}, baz) {

}
// Message: Duplicate @property "cfg.foo"

/**
 * @typedef (SomeType) SomeTypedef
 * @prop foo
 * @prop foo
 */
// Settings: {"jsdoc":{"tagNamePreference":{"property":"prop"}}}
// Message: Duplicate @prop "foo"

/**
 * @typedef (SomeType) SomeTypedef
 * @property foo
 */
// Settings: {"jsdoc":{"tagNamePreference":{"property":false}}}
// Message: Unexpected tag `@property`
````

The following patterns are not considered problems:

````js
/**
 *
 */

/**
 * @typedef (SomeType) SomeTypedef
 * @property foo
 */

/**
 * @typedef (SomeType) SomeTypedef
 * @prop foo
 */

/**
 * @typedef (SomeType) SomeTypedef
 * @property foo
 * @property bar
 */

/**
 * @typedef (SomeType) SomeTypedef
 * @property foo
 * @property foo.foo
 * @property bar
 */

/**
 * Assign the project to a list of employees.
 * @typedef (SomeType) SomeTypedef
 * @property {object[]} employees - The employees who are responsible for the project.
 * @property {string} employees[].name - The name of an employee.
 * @property {string} employees[].department - The employee's department.
 */

/**
 * @typedef (SomeType) SomeTypedef
 * @property {Error} error Exit code
 * @property {number} [code = 1] Exit code
 */

/**
 * @namespace (SomeType) SomeNamespace
 * @property {Error} error Exit code
 * @property {number} [code = 1] Exit code
 */

/**
 * @class
 * @property {Error} error Exit code
 * @property {number} [code = 1] Exit code
 */
function quux (code = 1) {
  this.error = new Error('oops');
  this.code = code;
}

/**
 * @typedef (SomeType) SomeTypedef
 * @property foo
 * @property foo.bar
 * @property foo.baz
 * @property bar
 */
````


<a name="eslint-plugin-jsdoc-rules-check-syntax"></a>

## Further Reading

* [eslint-plugin-jsdoc - check-property-names](https://github.com/gajus/eslint-plugin-jsdoc/blob/master/README.md#check-property-names)
