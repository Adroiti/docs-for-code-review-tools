Pattern: Disabled Container Insights for AWS ECS cluster

Issue: -

## Description

CloudWatch Container Insights provide more metrics and logs for container based applications and micro services.

**Resolution**: Enable Container Insights.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_ecs_cluster" "bad_example" {
  	name = "services-cluster"
}
```

Example of **correct** code:

```terraform
resource "aws_ecs_cluster" "good_example" {
	name = "services-cluster"
  
	setting {
	  name  = "containerInsights"
	  value = "enabled"
	}
}
```