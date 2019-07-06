Pattern: Escaping void return function

Issue: -

## Description

Flags functions that don't return anything, yet are wrapped in an escaping function call. E.g. `esc_html( _e( 'foo' ) );`

## Further Reading

* [WordPressVIPMinimum.Security.EscapingVoidReturnFunctions](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Security/EscapingVoidReturnFunctionsSniff.php)