Pattern: Allowed reuse of passwords for AWS IAM

Issue: -

## Description

IAM account password policies should prevent the reuse of passwords. The account password policy should be set to prevent using any of the last five used passwords.

**Resolution**: Prevent password reuse in the policy.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	password_reuse_prevention = 1
	# ...
}
```

Example of **correct** code:

```terraform
resource "aws_iam_account_password_policy" "good_example" {
	# ...
	password_reuse_prevention = 5
	# ...
}
```