Pattern: Bracket notation used where dot notation is possible

Issue: -

## Description

Using bracket notation when dot notation is possible makes code less readable. While bracket notation is necessary for dynamic property access or invalid identifiers, using it unnecessarily makes code more verbose and harder to understand.

## Examples

Example of **incorrect** code:
```ts
// Using brackets for simple property access
obj['name'];
user['firstName'];
settings['enabled'];

// Using brackets for method calls
object['toString']();
array['map'](x => x * 2);

class Example {
  private prop = 123;
  
  method() {
    // Using brackets for private access
    return this['prop'];
  }
}
```

Example of **correct** code:
```ts
// Using dot notation for simple property access
obj.name;
user.firstName;
settings.enabled;

// Using dot notation for method calls
object.toString();
array.map(x => x * 2);

// Using brackets for dynamic access
const key = getKey();
obj[key];

// Using brackets for invalid identifiers
obj['invalid-key'];
obj['class'];

// Using brackets for index signatures when configured
interface StringMap {
  [key: string]: any;
}
const map: StringMap = {};
const value = map['someKey'];
```