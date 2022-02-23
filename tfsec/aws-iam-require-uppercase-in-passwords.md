Pattern: Allowed non-uppercase passwords for AWS IAM policy

Issue: -

## Description

IAM account password policies should ensure that passwords content including at least one uppercase character.

**Resolution**: Enforce longer, more complex passwords in the policy.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# require_uppercase_characters not set
	# ...
}
```

Example of **correct** code:

```terraform
resource "aws_iam_account_password_policy" "good_example" {
	# ...
	require_uppercase_characters = true
	# ...
}
```