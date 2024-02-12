Pattern: Use of inline tabs

Issue: -

## Description

Enforces using spaces for mid-line alignment.

While tab versus space based indentation is a question of preference, for mid-line alignment, spaces should always be preferred, as using tabs will result in inconsistent formatting depending on the dev-user's chosen tab width.

> _This sniff is especially useful for tab-indentation based standards which use the `Generic.Whitespace.DisallowSpaceIndent` sniff to enforce this._
>
> **DO** make sure to set the PHPCS native `tab-width` configuration for the best results.
> ```xml
>    <arg name="tab-width" value="4"/>
> ```
>
> The PHPCS native `Generic.Whitespace.DisallowTabIndent` sniff (used for space-based standards) oversteps its reach and silently does mid-line tab to space replacements as well.
> However, the sister-sniff `Generic.Whitespace.DisallowSpaceIndent` leaves mid-line tabs/spaces alone.
> This sniff fills that gap.


## Further Reading

* [Universal.WhiteSpace.DisallowInlineTabs](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#universal)