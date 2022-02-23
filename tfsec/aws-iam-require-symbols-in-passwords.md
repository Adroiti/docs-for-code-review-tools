Pattern: Allowed non-symbol passwords for AWS IAM policy

Issue: -

## Description

IAM account password policies should ensure that passwords content including a symbol.

**Resolution**: Enforce longer, more complex passwords in the policy.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# require_symbols not set
	# ...
}
```

Example of **correct** code:

```terraform
resource "aws_iam_account_password_policy" "good_example" {
	# ...
	require_symbols = true
	# ...
}
```