Pattern: Unsafe merging of class and interface

Issue: -

## Description

Merging class and interface declarations with the same name creates unsafe situations because TypeScript doesn't verify property initialization. This can lead to runtime errors when accessing properties that TypeScript believed existed but were never initialized.

## Examples

Example of **incorrect** code:
```ts
interface Foo {
  nums: number[];
}

class Foo {}

// This will cause runtime error:
const foo = new Foo();
foo.nums.push(1); // Runtime Error: Cannot read properties of undefined
```

Example of **correct** code:
```ts
interface Foo {}
class Bar implements Foo {}

namespace Baz {}
namespace Baz {}
enum Baz {}

namespace Qux {}
function Qux() {}
```