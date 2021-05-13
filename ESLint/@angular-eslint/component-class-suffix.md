Pattern: Malformed component suffix

Issue: -

## Description

This rule follows the recommendation from the [Angular styleguide](https://angular.io/guide/styleguide#style-02-03).

Examples of **incorrect** code for this rule (with default configuration):

```ts
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
})
class App {}
```

Example of **correct** code for this rule:

```ts
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
})
class AppComponent {}
```

## Options

By default, the suffix will be `Component`. You may pass an array of suffixes, for example:

```json
{
  "@angular-eslint/component-class-suffix": [
    "error",
    {
      "suffixes": ["Component", "Comp"]
    }
  ]
}
```

Examples of **incorrect** code with the above options:

```ts
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
})
export class AppCompe {}

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
})
export class App {}
```

Example of **correct** code with the above options:

```ts
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
})
export class AppComp {}

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
})
export class AppComponent {}
```

## Further Reading

* [GitHub - jsx-import](https://github.com/angular-eslint/angular-eslint/blob/master/packages/eslint-plugin/docs/rules/component-class-suffix.md)