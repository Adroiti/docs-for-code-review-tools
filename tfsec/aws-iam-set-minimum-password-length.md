Pattern: Allowed short passwords for AWS IAM policy

Issue: -

## Description

IAM account password policies should ensure that passwords have a minimum length. The account password policy should be set to enforce minimum password length of at least `14` characters.

**Resolution**: Enforce longer, more complex passwords in the policy.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# minimum_password_length not set
	# ...
}
```

Example of **correct** code:

```terraform
resource "aws_iam_account_password_policy" "good_example" {
	# ...
	minimum_password_length = 14
	# ...
}
```