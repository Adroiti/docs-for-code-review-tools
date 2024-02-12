Pattern: Both function and OO declarations

Issue: -

## Description

Enforces for a file to either declare (global/namespaced) functions or declare OO structures, but not both.

* Nested function declarations, i.e. functions declared within a function/method will be disregarded for the purposes of this sniff.
    The same goes for anonymous classes, closures and arrow functions.
* Note: This sniff has no opinion on side effects. If you want to sniff for those, use the PHPCS native `PSR1.Files.SideEffects` sniff.
* Also note: This sniff has no opinion on multiple OO structures being declared in one file.
    If you want to sniff for that, use the PHPCS native `Generic.Files.OneObjectStructurePerFile` sniff.

## Further Reading

* [Universal.Files.SeparateFunctionsFromOO](https://github.com/PHPCSStandards/PHPCSExtra?tab=readme-ov-file#universal)