Pattern: Disabled domain encryption for AWS Elasticsearch

Issue: -

## Description

You should ensure your Elasticsearch data is encrypted at rest to help prevent sensitive information from being read by unauthorized users.

**Resolution**: Enable Elasticsearch domain encryption.

## Examples

The following example will fail the aws-elastic-search-enable-domain-encryption check.

```terraform
 resource "aws_elasticsearch_domain" "bad_example" {
   domain_name = "domain-foo"
 
   encrypt_at_rest {
     enabled = false
   }
 }
 
```

The following example will pass the aws-elastic-search-enable-domain-encryption check.

```terraform
 resource "aws_elasticsearch_domain" "good_example" {
   domain_name = "domain-foo"
 
   encrypt_at_rest {
     enabled = true
   }
 }
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticsearch_domain#encrypt_at_rest](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticsearch_domain#encrypt_at_rest)
- [https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/encryption-at-rest.html](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/encryption-at-rest.html)