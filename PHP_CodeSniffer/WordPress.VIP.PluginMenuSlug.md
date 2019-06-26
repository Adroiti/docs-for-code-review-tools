Pattern: Use of `__FILE__` for page registration

Issue: -

## Description

When adding menus or registering your plugins, make sure that you use an unique handle or slug other than `__FILE__` to ensure that you are not revealing system paths.

## Further Reading

* [VIP Go](https://vip.wordpress.com/documentation/vip-go/code-review-blockers-warnings-notices/#using-__file__-for-page-registration)
