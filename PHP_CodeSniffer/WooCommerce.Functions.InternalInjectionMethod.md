Pattern: Malformed internal injection method

Issue: -

## Description

Eevaluates whether or not a dependency injection method meets our criteria:

    Must be final and public
    Must have an `@internal` annotation


## Further Reading

* [WooCommerce.Functions.InternalInjectionMethod](https://github.com/woocommerce/woocommerce-sniffs/blob/master/src/WooCommerce/Sniffs/Functions/InternalInjectionMethodSniff.php)