Pattern: Missing use of managed keys for Google storage disk

Issue: -

## Description

Using unmanaged keys makes rotation and general management difficult.

**Resolution**: Use managed keys.

## Examples

Example of **incorrect** code:

```terraform
resource "google_compute_disk" "bad_example" {
  name  = "test-disk"
  type  = "pd-ssd"
  zone  = "us-central1-a"
  image = "debian-9-stretch-v20200805"
  labels = {
    environment = "dev"
  }
  physical_block_size_bytes = 4096
}
```

Example of **correct** code:

```terraform
resource "google_compute_disk" "good_example" {
  name  = "test-disk"
  type  = "pd-ssd"
  zone  = "us-central1-a"
  image = "debian-9-stretch-v20200805"
  labels = {
    environment = "dev"
  }
  physical_block_size_bytes = 4096
  disk_encryption_key {
    kms_key_self_link = "something"
  }
}
```