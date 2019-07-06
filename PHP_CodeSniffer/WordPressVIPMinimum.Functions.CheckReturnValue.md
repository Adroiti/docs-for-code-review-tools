Pattern: Missing check for function return value

Issue: -

## Description

This sniff enforces checking the return value of a function before passing it to another one.

An example of a not checking return value is:

``` php
echo esc_url( wpcom_vip_get_term_link( $term ) );
```

## Further Reading

* [WordPressVIPMinimum.Functions.CheckReturnValue](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Functions/CheckReturnValueSniff.php)