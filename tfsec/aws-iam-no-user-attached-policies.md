Pattern: Use of AWS IAM policy for user

Issue: -

## Description

CIS recommends that you apply IAM policies directly to groups and roles but not users. Assigning privileges at the group or role level reduces the complexity of access management as the number of users grow. Reducing access management complexity might in turn reduce opportunity for a principal to inadvertently receive or retain excessive privileges.

**Resolution**: Grant policies at the group level instead.

## Examples

The following example will fail the aws-iam-no-user-attached-policies check.
```terraform

resource "aws_iam_user" "jim" {
  name = "jim"
}

resource "aws_iam_user_policy" "ec2policy" {
  name = "test"
  user = aws_iam_user.jim.name

  policy = <<EOF
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "ec2:Describe*"
      ],
      "Effect": "Allow",
      "Resource": "*"
    }
  ]
}
EOF
}
 			
```

The following example will pass the aws-iam-no-user-attached-policies check.
```terraform

resource "aws_iam_group" "developers" {
  name = "developers"
  path = "/users/"
}

resource "aws_iam_user" "jim" {
  name = "jim"
}

resource "aws_iam_group_membership" "devteam" {
  name = "developers-team"

  users = [
    aws_iam_user.jim.name,
  ]

  group = aws_iam_group.developers.name
}

resource "aws_iam_group_policy" "ec2policy" {
  name = "test"
  group = aws_iam_group.developers.name

  policy = <<EOF
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "ec2:Describe*"
      ],
      "Effect": "Allow",
      "Resource": "*"
    }
  ]
}
EOF
}
 			
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_user](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_user)
- [https://console.aws.amazon.com/iam/](https://console.aws.amazon.com/iam/)