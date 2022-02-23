Pattern: Disabled in-transit encryption for AWS Elasticsearch

Issue: -

## Description

Traffic flowing between Elasticsearch nodes should be encrypted to ensure sensitive data is kept private.

**Resolution**: Enable encrypted node to node communication.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_elasticsearch_domain" "bad_example" {
  domain_name = "domain-foo"

  node_to_node_encryption {
    enabled = false
  }
}
```

Example of **correct** code:

```terraform
resource "aws_elasticsearch_domain" "good_example" {
  domain_name = "domain-foo"

  node_to_node_encryption {
    enabled = true
  }
}
```