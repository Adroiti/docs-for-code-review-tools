Pattern: Inconsistent spacing for array braces

Issue: -

## Description

Enforce consistent spacing for the open/close braces of array declarations.

The sniff allows for having different settings for:
- Space between the array keyword and the open parenthesis for long arrays via the `keywordSpacing` property.
    Accepted values: (int) number of spaces or `false` to turn this check off. Defaults to `0` spaces.
- Spaces on the inside of the braces for empty arrays via the `spacesWhenEmpty` property.
    Accepted values: (string) `newline`, (int) number of spaces or `false` to turn this check off. Defaults to `0` spaces.
- Spaces on the inside of the braces for single-line arrays via the `spacesSingleLine` property;
    Accepted values: (int) number of spaces or `false` to turn this check off. Defaults to `0` spaces.
- Spaces on the inside of the braces for multi-line arrays via the `spacesMultiLine` property.
    Accepted values: (string) `newline`, (int) number of spaces or `false` to turn this check off. Defaults to `newline`.

Note: if any of the above properties are set to `newline`, it is recommended to also include an array indentation sniff. This sniff will not handle the indentation.

## Further Reading

* [NormalizedArrays.Arrays.ArrayBraceSpacing](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#normalizedarrays)