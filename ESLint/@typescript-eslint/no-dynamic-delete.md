Pattern: Dynamic property deletion with computed key

Issue: -

## Description

Using the delete operator with dynamically computed property keys can lead to dangerous and unoptimized code. When removing properties from objects, using dynamic keys makes it difficult to track which properties are being removed and can accidentally affect hidden properties or prototype chain properties.

## Examples

Example of **incorrect** code:
```ts
// Computed property deletion
const key = 'someProp';
delete obj[key];

// Expression-based deletion
delete obj[key.toUpperCase()];

// Variable access deletion
const propName = 'dangerous';
delete user[propName];

// Method result deletion
delete data[getKeyToRemove()];
```

Example of **correct** code:
```ts
// Static property deletion
delete obj.unwantedProp;

// Numeric index deletion
delete items[0];
delete items[-1];

// String literal deletion
delete config['api-key'];

// Consider using Map/Set instead
const dataMap = new Map();
dataMap.delete(key);

// Or filtering/reconstructing objects
const { [keyToRemove]: _, ...rest } = object;
```