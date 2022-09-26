Pattern: Use of root user access key for AWS IAM

Issue: -

## Description

CIS recommends that all access keys be associated with the root user be removed. Removing access keys associated with the root user limits vectors that the account can be compromised by. Removing the root user access keys also encourages the creation and use of role-based accounts that are least privileged.

**Resolution**: Use lower privileged accounts instead, so only required privileges are available.

## Examples

The following example will fail the aws-iam-no-root-access-keys check.
```terraform

resource "aws_iam_access_key" "good_example" {
 	user = "root"
}
 			
```

The following example will pass the aws-iam-no-root-access-keys check.
```terraform

resource "aws_iam_access_key" "good_example" {
 	user = "lowprivuser"
}
 			
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_access_key](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_access_key)
- [https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)