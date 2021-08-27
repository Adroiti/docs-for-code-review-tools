Pattern: Use of plaintext for Disk encryption key

Issue: -

## Description

Providing your encryption key in plaintext format means anyone with access to the source code also has access to the key.

**Resolution**: Use managed keys or provide the raw key via a secrets manager.

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
  disk_encryption_key {
    raw_key = "something"
  }
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
}
```