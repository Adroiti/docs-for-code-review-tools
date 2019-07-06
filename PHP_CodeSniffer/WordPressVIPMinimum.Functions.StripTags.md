Pattern: Use of improper tag stripping

Issue: -

## Description

`strip_tags()` does not strip CSS and JS in between the script and style tags. Use `wp_kses()` to allow only the HTML you need or `wp_strip_all_tags()` to strip all tags.

## Further Reading

* [WordPressVIPMinimum.Functions.StripTags](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Functions/StripTagsSniff.php)