Pattern: Missing `key` prop

Issue: -

## Description

Disallow missing `key` props in iterators/collection literals. The key prop allows for improved rendering performance.

## Examples

Example of **incorrect** code:

```jsx
import { component$ } from '@builder.io/qwik';
 
export const Person = component$(() => {
  const person  = {
    firstName: 'John',
    lastName: 'Doe',
    age: 32,
  }
 
  return (
    <ul>
      {Object.keys(person).map((color) => (
        <li>{person[key]}</li>
      )}
    </ul>
  );
});
```

Example of **correct** code:

```jsx
import { component$ } from '@builder.io/qwik';
 
export const Person = component$(() => {
  const person  = {
    firstName: 'John',
    lastName: 'Doe',
    age: 32,
  }
 
  return (
    <ul>
      {Object.keys(person).map((color) => (
        <li key={`person-${key}`}>{person[key]}</li>
      )}
    </ul>
  );
});
```
