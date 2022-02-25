Pattern: Use of plain-text for GitHub Action secret

Issue: -

## Description

For the purposes of security, the contents of the `plaintext_value` field have been marked as sensitive to Terraform, but this does not hide it from state files. State should be always treated as sensitive.

**Resolution**: Do not store plaintext values in your code but rather populate the `encrypted_value` using fields from a resource, data source or variable.

## Examples

The following example will fail the github-actions-no-plain-text-action-secrets check.

```terraform
resource "github_actions_environment_secret" "bad_example" {	 
	repository       = "my repository name"
	environment       = "my environment"
	secret_name       = "my secret name"
	plaintext_value   = "sensitive secret string"
}
```

The following example will pass the github-actions-no-plain-text-action-secrets check.

```terraform
resource "github_actions_environment_secret" "good_example" {
	repository       = "my repository name"
	environment       = "my environment"
	secret_name       = "my secret name"
	encrypted_value   = var.some_encrypted_secret_string
}
```

## Further reading

- [https://registry.terraform.io/providers/integrations/github/latest/docs/resources/actions_environment_secret](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/actions_environment_secret)
- [https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)
- [https://registry.terraform.io/providers/integrations/github/latest/docs/resources/actions_environment_secret](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/actions_environment_secret)
- [https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)