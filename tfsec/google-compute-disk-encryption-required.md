Pattern: Use of plain-text key for Google Compute disk encryption

Issue: -

## Description

Sensitive values such as raw encryption keys should not be included in your Terraform code, and should be stored securely by a secrets manager.

**Resolution**: Reference a managed key rather than include the key in raw format.

## Examples

Example of **incorrect** code:

```terraform
resource "google_compute_disk" "good_example" {
	disk_encryption_key {
		raw_key="b2ggbm8gdGhpcyBpcyBiYWQ="
	}
}
```

Example of **correct** code:

```terraform
resource "google_compute_disk" "good_example" {
	disk_encryption_key {
		kms_key_self_link = google_kms_crypto_key.my_crypto_key.id
	}
}
```