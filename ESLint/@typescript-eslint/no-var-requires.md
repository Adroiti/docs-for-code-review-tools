Pattern: Variable require statement

Issue: -

## Description

Using `require` with variable declarations (`var`, `let`, or `const`) is discouraged in favor of ES6-style imports or TypeScript's `import foo = require('foo')` syntax. This ensures consistent module usage patterns and better TypeScript integration.

## Examples

Example of **incorrect** code:
```ts
var foo = require('foo');
const foo = require('foo');
let foo = require('foo');
```

Example of **correct** code:
```ts
import foo = require('foo');
require('foo');
import foo from 'foo';
```