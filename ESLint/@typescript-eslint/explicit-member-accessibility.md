Pattern: Missing accessibility modifier in class member

Issue: -

## Description

While TypeScript members are public by default, missing explicit accessibility modifiers (public, private, protected) can make code intent less clear. In large codebases, implicit accessibility can make it harder to enforce proper encapsulation and maintain class boundaries.

## Examples

Example of **incorrect** code:
```ts
class User {
  // Missing modifiers on properties
  name: string;
  id: number;
  
  // Missing modifier on constructor
  constructor(name: string, id: number) {
    this.name = name;
    this.id = id;
  }
  
  // Missing modifiers on methods
  getData() {
    return { name: this.name, id: this.id };
  }
  
  setName(name: string) {
    this.name = name;
  }
}

class Animal {
  // Missing modifiers on accessors
  get species() { 
    return this._species;
  }
  set species(value: string) {
    this._species = value;
  }
}
```

Example of **correct** code:
```ts
class User {
  // Explicit modifiers on properties
  private name: string;
  public id: number;
  
  // Explicit modifier on constructor
  public constructor(name: string, id: number) {
    this.name = name;
    this.id = id;
  }
  
  // Explicit modifiers on methods
  public getData() {
    return { name: this.name, id: this.id };
  }
  
  private setName(name: string) {
    this.name = name;
  }
}

class Animal {
  private _species: string;
  
  // Explicit modifiers on accessors
  public get species() {
    return this._species;
  }
  protected set species(value: string) {
    this._species = value;
  }

  // Parameter property with explicit modifier
  constructor(private age: number) {}
}
```