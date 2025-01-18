Pattern: Function declaration inside loop

Issue: -

## Description

Declaring functions inside loop statements can lead to unexpected behavior due to the way closures capture variables. Each iteration creates a new function that references loop variables, but these references share the same scope, potentially causing bugs with variable values.

## Examples

Example of **incorrect** code:
```ts
// Function using loop counter
for (let i = 0; i < 10; i++) {
  funcs[i] = function() {
    return i;
  };
}

// Function using loop variable
for (const item of items) {
  callbacks.push(function() {
    console.log(item);
  });
}

// Arrow function in while loop
while (condition) {
  const handler = () => {
    process(value);
  };
  register(handler);
}

// Function using loop-declared variable
for (let i = 0; i < 10; i++) {
  const value = items[i];
  listeners[i] = function() {
    return value;
  };
}
```

Example of **correct** code:
```ts
// Function factory outside loop
function createHandler(index: number) {
  return function() {
    return index;
  };
}
for (let i = 0; i < 10; i++) {
  funcs[i] = createHandler(i);
}

// Using forEach with proper scope
items.forEach((item) => {
  const handler = () => {
    console.log(item);
  };
  callbacks.push(handler);
});

// Immediate invocation to create proper scope
for (let i = 0; i < 10; i++) {
  listeners[i] = ((value) => {
    return () => value;
  })(items[i]);
}

// Moving function outside loop
const handler = (value: string) => {
  process(value);
};
while (condition) {
  register(handler);
}
```