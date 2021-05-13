Pattern: Missing use of `takeUntil`

Issue: -

## Description

This rule effects failures if `subscribe` is called within a component and the `takeUntil`-destroyed pattern is not used.

Examples of **incorrect** code for this rule:

```ts
import { Component, OnInit } from "@angular/core";
import { switchMap } from "rxjs/operators";

@Component({
  selector: "some-component"
})
class SomeComponent implements OnInit {
  // ...
  ngOnInit() {
    this.values.pipe(
      switchMap((value) => something(value))
    ).subscribe();
  }
}
```

Examples of **correct** code for this rule:

```ts
import { Component, OnDestroy, OnInit } from "@angular/core";
import { switchMap } from "rxjs/operators";

@Component({
  selector: "some-component"
})
class SomeComponent implements OnDestroy, OnInit {
  private destroy = new Subject<void>();
  // ...
  ngOnInit() {
    this.values.pipe(
      switchMap((value) => something(value)),
      takeUntil(this.destroy)
    ).subscribe();
  }
  ngOnDestroy() {
    this.destroy.next();
    this.destroy.complete();
  }
}
```

## Further Reading

* [GitHub - prefer-takeuntil](https://github.com/cartant/eslint-plugin-rxjs-angular/blob/main/docs/rules/prefer-takeuntil.md)