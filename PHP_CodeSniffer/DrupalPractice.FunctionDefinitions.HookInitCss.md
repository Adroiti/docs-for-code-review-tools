Pattern: Use of `drupal_add_css`/`drupal_add_js` in `hook_init`/`hook_page_build`

Issue: -

## Description

Checks that `drupal_add_css()` is not used in `hook_init()`.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionDefinitions.HookInitCss](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionDefinitions/HookInitCssSniff.php)