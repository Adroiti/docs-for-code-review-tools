Pattern: Missing use of `all_regions` for AWS configuration aggregator

Issue: -

## Description

The configuration aggregator should be configured with `all_regions` for the source. This will help limit the risk of any un-monitored configurations in regions that are thought to be unused.

**Resolution**: Set the aggregator to cover all regions.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_config_configuration_aggregator" "bad_example" {
	name = "example"
	  
	account_aggregation_source {
	  account_ids = ["123456789012"]
	  regions     = ["us-west-2", "eu-west-1"]
	}
}
```

Example of **correct** code:

```terraform
resource "aws_config_configuration_aggregator" "good_example" {
	name = "example"
	  
	account_aggregation_source {
	  account_ids = ["123456789012"]
	  all_regions = true
	}
}
```