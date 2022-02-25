Pattern: Use of plain-text for Google Compute disk encryption

Issue: -

## Description

Sensitive values such as raw encryption keys should not be included in your Terraform code, and should be stored securely by a secrets manager.

**Resolution**: Reference a managed key rather than include the key in raw format.

## Examples

The following example will fail the google-compute-disk-encryption-no-plaintext-key check.

```terraform
 resource "google_compute_disk" "good_example" {
 	disk_encryption_key {
 		raw_key="b2ggbm8gdGhpcyBpcyBiYWQ="
 	}
 }
```

The following example will pass the google-compute-disk-encryption-no-plaintext-key check.

```terraform
 resource "google_compute_disk" "good_example" {
 	disk_encryption_key {
 		kms_key_self_link = google_kms_crypto_key.my_crypto_key.id
 	}
 }
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_disk#kms_key_self_link](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_disk#kms_key_self_link)
- [https://cloud.google.com/compute/docs/disks/customer-supplied-encryption](https://cloud.google.com/compute/docs/disks/customer-supplied-encryption)