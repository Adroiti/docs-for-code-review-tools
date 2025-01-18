Pattern: Variable or type redeclaration

Issue: -

## Description

Redeclaring the same variable or type name can lead to confusion and bugs. While TypeScript supports certain forms of declaration merging (for interfaces, namespaces, etc.), accidentally redeclaring variables or mixing value/type declarations with the same name should be avoided.

## Examples

Example of **incorrect** code:
```ts
// Variable redeclaration
var x = 1;
var x = 2;

// Mixing type and variable declarations
type User = { name: string };
const User = { name: 'John' };

// Function redeclaration
function f() {}
function f() {}

// Class redeclaration
class C {}
class C {}

// Enum redeclaration
enum E {}
enum E {}

// Variable shadowing in blocks
function test() {
  let x = 1;
  if (true) {
    let x = 2;
  }
}
```

Example of **correct** code:
```ts
// Declaration merging (when allowed)
interface User {
  name: string;
}
interface User {
  age: number;
}

// Namespace merging
namespace API {
  export const x = 1;
}
namespace API {
  export const y = 2;
}

// Class and namespace merging
class Service {}
namespace Service {
  export const version = '1.0';
}

// Different names for type and value
type UserType = { name: string };
const UserImpl = { name: 'John' };

// Unique variable names
function test() {
  let x = 1;
  if (true) {
    let y = 2;
  }
}
```