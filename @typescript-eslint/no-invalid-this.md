Pattern: Invalid this reference outside class context

Issue: -

## Description

Using the 'this' keyword outside of class-like contexts can lead to runtime errors or unexpected behavior. JavaScript's 'this' binding rules are complex, and improper usage outside of classes or objects can result in undefined or incorrect references.

## Examples

Example of **incorrect** code:
```ts
// 'this' in regular function
function showValue() {
  console.log(this.value);
}

// 'this' in arrow function outside class
const getValue = () => {
  return this.value;
};

// Standalone 'this' usage
const value = this.something;

// 'this' in callback without binding
element.addEventListener('click', function() {
  this.handleClick();
});
```

Example of **correct** code:
```ts
// 'this' in class method
class Example {
  value = 42;
  
  getValue() {
    return this.value;
  }

  // Arrow function preserving 'this'
  boundMethod = () => {
    return this.value;
  }
}

// 'this' parameter type annotation
function listener(this: HTMLElement, e: Event) {
  this.innerHTML = 'Clicked';
}

// Explicitly bound function
const obj = {
  value: 123,
  getValue: function() {
    return this.value;
  }
};

// Proper event listener binding
element.addEventListener('click', this.handleClick.bind(this));
```