Pattern: Use of `$_SERVER['REMOTE_ADDR']`

Issue: -

## Description

Make sure that `ip_address()` or `Drupal::request()->getClientIp()` is used instead of
`$_SERVER['REMOTE_ADDR']`.

## Further Reading

* [PHP_CodeSniffer - Drupal.Semantics.RemoteAddress](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/Drupal/Sniffs/Semantics/RemoteAddressSniff.php)