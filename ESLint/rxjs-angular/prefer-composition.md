Pattern: Prefer composition

Issue: -

## Description

This rule effects failures if `subscribe` calls are made with a component and the returned subscription is not composed into a subscription that is unsubscribed when the component is destroyed.

Examples of **incorrect** code for this rule:

```ts
import { Component, OnDestroy, OnInit } from "@angular/core";
import { Subscription } from "rxjs";

@Component({
  selector: "some-component",
  template: "<span>{{ value }}</span>"
})
export class SomeComponent implements OnInit {
  value: string;
  // ...
  ngOnInit() {
    this.values.subscribe(value => this.value = value);
  }
}
```

Examples of **correct** code for this rule:

```ts
import { Component, OnDestroy, OnInit } from "@angular/core";
import { Subscription } from "rxjs";

@Component({
  selector: "some-component",
  template: "<span>{{ value }}</span>"
})
export class SomeComponent implements OnInit, OnDestroy {
  value: string;
  private subscription = new Subscription();
  // ...
  ngOnInit() {
    this.subscription.add(this.values.subscribe(value => this.value = value));
  }
  ngOnDestroy() {
    this.subscription.unsubscribe();
  }
}
```

## Further Reading

* [GitHub - prefer-composition](https://github.com/cartant/eslint-plugin-rxjs-angular/blob/main/docs/rules/prefer-composition.md)