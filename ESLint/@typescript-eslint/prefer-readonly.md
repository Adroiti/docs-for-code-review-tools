Pattern: Private member without readonly modifier

Issue: -

## Description

Private class members (using either `private` or `#`) that are never modified after their initialization should be marked as `readonly` to enforce immutability and better signal the developer's intent. This includes members that are only set in the constructor.

## Examples

Example of **incorrect** code:
```ts
class Container {
  private neverModifiedMember = true;
  private onlyModifiedInConstructor: number;
  #neverModifiedPrivateField = 3;

  public constructor(
    onlyModifiedInConstructor: number,
    private neverModifiedParameter: string,
  ) {
    this.onlyModifiedInConstructor = onlyModifiedInConstructor;
  }
}
```

Example of **correct** code:
```ts
class Container {
  private readonly neverModifiedMember = true;
  private readonly onlyModifiedInConstructor: number;
  readonly #neverModifiedPrivateField = 3;

  public constructor(
    onlyModifiedInConstructor: number,
    private readonly neverModifiedParameter: string,
  ) {
    this.onlyModifiedInConstructor = onlyModifiedInConstructor;
  }

  // Members that are modified later are correctly not readonly
  private modifiedLater = 'unchanged';
  public mutate() {
    this.modifiedLater = 'changed';
  }
}
```