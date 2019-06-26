Pattern: Misuse of `$wpdb->prepare()`

Issue: -

## Description

Check for incorrect use of the `$wpdb->prepare` method.

Check the following issues:
- The only placeholders supported are: %d, %f (%F) and %s and their variations.
- Literal % signs need to be properly escaped as `%%`.
- Simple placeholders (%d, %f, %F, %s) should be left unquoted in the query string.
- Complex placeholders - numbered and formatted variants - will not be quoted
  automagically by `$wpdb->prepare()`, so if used for values, should be quoted in
  the query string.
- Either an array of replacements should be passed matching the number of
  placeholders found or individual parameters for each placeholder should
  be passed.
- Wildcards for LIKE compare values should be passed in via a replacement parameter.

The rule allows for a specific pattern with a variable number of placeholders
created using code along the lines of:
`sprintf( 'query .... IN (%s) ...', implode( ',', array_fill( 0, count( $something ), '%s' ) ) )`.

A "PreparedSQLPlaceholders replacement count" whitelist comment is supported
specifically to silence the `ReplacementsWrongNumber` and `UnfinishedPrepare`
error codes. The other error codes are not affected by it.

## Further Reading

* [WordPress.DB.PreparedSQLPlaceholders](https://developer.wordpress.org/reference/classes/wpdb/prepare)
* [WordPress.DB.PreparedSQLPlaceholders](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/DB/PreparedSQLPlaceholdersSniff.php)