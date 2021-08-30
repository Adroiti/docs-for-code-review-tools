Pattern: IAM customer managed policies should not allow decryption actions on all KMS keys

Issue: -

## Description

IAM policies define which actions an identity (user, group, or role) can perform on which resources. Following security best practices, AWS recommends that you allow least privilege. In other words, you should grant to identities only the kms:Decrypt or kms:ReEncryptFrom permissions and only for the keys that are required to perform a task.

**Resolution**: Scope down the resources of the IAM policy to specific keys.

## Examples

Example of **incorrect** code:

```terraform
data "aws_iam_policy_document" "kms_policy" {
  statement {
    principals {
      type        = "AWS"
      identifiers = ["arn:aws:iam::${data.aws_caller_identity.current.account_id}:root"]
    }
    actions   = ["kms:*"]
    resources = ["*"]
  }
}
```

Example of **correct** code:

```terraform
data "aws_iam_policy_document" "kms_policy" {
  statement {
    principals {
      type        = "AWS"
      identifiers = ["arn:aws:iam::${data.aws_caller_identity.current.account_id}:root"]
    }
    actions   = ["kms:*"]
    resources = [aws_kms_key.main.arn]
  }
}
```