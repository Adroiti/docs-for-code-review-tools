Pattern: Use of unexpected hack

Issue: -

## Description

Disallows browser hacks that are irrelevant to the browsers you are targeting, using stylehacks.

## Examples

The following patterns are considered violations:

```css
a { color/*\**/: pink\9; }
```

As this hack targets IE7-8.

## Further Reading

* [GitHub - stylelint-no-browser-hacks](https://github.com/Slamdunk/stylelint-no-browser-hacks)