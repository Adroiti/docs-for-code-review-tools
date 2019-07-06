Pattern: `WP_Query` modified without `is_main_query()` check

Issue: -

## Description

Validates a proper usage of `pre_get_posts` action callback. It looks for cases when the `WP_Query object` is being modified without checking for `WP_Query::is_main_query()`.

## Further Reading

* [WordPressVIPMinimum.Hooks.PreGetPosts](https://github.com/Automattic/VIP-Coding-Standards/tree/develop/WordPressVIPMinimum/Sniffs/Hooks/PreGetPostsSniff.php)