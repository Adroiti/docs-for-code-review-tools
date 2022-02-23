Pattern: Use of public cluster access for AWS EKS

Issue: -

## Description

EKS clusters are available publicly by default, this should be explicitly disabled in the `vpc_config` of the EKS cluster resource.

**Resolution**: Don't enable public access to EKS Clusters.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_eks_cluster" "bad_example" {
    // other config 

    name = "bad_example_cluster"
    role_arn = var.cluster_arn
    vpc_config {
		endpoint_public_access = true
		public_access_cidrs = ["0.0.0.0/0"]
    }
}
```

Example of **correct** code:

```terraform
resource "aws_eks_cluster" "good_example" {
    // other config 

    name = "good_example_cluster"
    role_arn = var.cluster_arn
    vpc_config {
        endpoint_public_access = false
    }
}
```