Pattern: Class name return type over this type

Issue: -

## Description

Using a class name as a return type instead of the polymorphic `this` type makes method chaining harder in extending classes. When methods return the class name type rather than `this`, calling those methods from a derived class will return objects typed as the base class, preventing access to derived class methods.

## Examples

Example of **incorrect** code:
```ts
class Foo {
  f1(): Foo {
    return this;
  }
  f2 = (): Foo => {
    return this;
  };
  f3(): Foo | undefined {
    return Math.random() > 0.5 ? this : undefined;
  }
}

// This causes problems in derived classes:
class Dog extends Animal {
  bark(): Dog { return this; }
}
const dog = new Dog();
dog.eat().bark(); // Error: bark doesn't exist on Animal
```

Example of **correct** code:
```ts
class Foo {
  f1(): this {
    return this;
  }
  f2() {
    return this;
  }
  f3 = (): this => {
    return this;
  };
  f4 = () => {
    return this;
  };
}

// When returning base class is intentional
class Derived extends Base {
  f(): Base {
    return this;
  }
}
```