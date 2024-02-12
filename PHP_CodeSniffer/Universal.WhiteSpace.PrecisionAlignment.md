Pattern: Inconsistent whitespace precision

Issue: -

## Description

Enforces code indentation to always be a multiple of a tabstop, i.e. disallow precision alignment.

Note:
* This sniff does not concern itself with tabs versus spaces.
    It is recommended to use the sniff in combination with the PHPCS native `Generic.WhiteSpace.DisallowTabIndent` or the `Generic.WhiteSpace.DisallowSpaceIndent` sniff.
* When using this sniff with tab-based standards, please ensure that the `tab-width` is set and either don't set the `$indent` property or set it to the tab-width (or a multiple thereof).
* The fixer works based on "best guess" and may not always result in the desired indentation. Combine this sniff with the `Generic.WhiteSpace.ScopeIndent` sniff for more precise indentation fixes.

The behaviour of the sniff is customizable via the following properties:
* `indent`: the indent used for the codebase.
    Accepted values: (int|null) number of spaces. Defaults to `null`.
    If this property is not set, the sniff will look to the `--tab-width` CLI value.
    If that also isn't set, the default tab-width of `4` will be used.
* `ignoreAlignmentBefore`: allows for providing a list of token names for which (preceding) precision alignment should be ignored.
    Accepted values: (array<string>) token constant names. Defaults to an empty array.
    Usage example:
    ```xml
    <rule ref="Universal.WhiteSpace.PrecisionAlignment">
       <properties>
           <property name="ignoreAlignmentBefore" type="array">
               <!-- Ignore precision alignment in inline HTML -->
               <element value="T_INLINE_HTML"/>
               <!-- Ignore precision alignment in multiline chained method calls. -->
               <element value="T_OBJECT_OPERATOR"/>
               <element value="T_NULLSAFE_OBJECT_OPERATOR"/>
           </property>
       </properties>
    </rule>
   ```
* `ignoreBlankLines`: whether or not potential trailing whitespace on otherwise blank lines should be examined or ignored.
    It is recommended to only set this to `false` if the standard including this sniff does not include the `Squiz.WhiteSpace.SuperfluousWhitespace` sniff (which is included in most standards).
    Accepted values: (bool)`true`|`false`. Defaults to `true`.

## Further Reading

* [Universal.WhiteSpace.PrecisionAlignment](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#universal)