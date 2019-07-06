Pattern: Extending `WP_CLI_Command`

Issue: -

## Description

Extend `WPCOM_VIP_CLI_Command` instead of `WP_CLI_Command` and use the helper functions available in it (such as `stop_the_insanity()`).

## Further Reading

* [Writing custom WP-CLI commands](https://wpvip.com/documentation/writing-custom-wp-cli-commands/)
* [WordPressVIPMinimum.Classes.RestrictedExtendClasses](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Classes/RestrictedExtendClassesSniff.php)