Pattern: Missing use of variable 

Issue: -

## Description

Preprocessers like SCSS, Less uses variables to make the code clean, maintainable and reusable. This rule enforces the use of variables based on custom configuration.

Example of **incorrect** code:

```css
$some-cool-color: #efefef;

.panel {
    display: inline-block;
    text-align: center;
    color: #efefef; // Wait a min! there should be a variable.
}
```

Example of **correct** code:

```css
$some-cool-color: #efefef;

.panel {
    display: inline-block;
    text-align: center;
    color: $some-cool-color;
}
```
