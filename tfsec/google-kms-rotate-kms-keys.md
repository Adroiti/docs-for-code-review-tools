Pattern: Unset key rotation period for Google KMS

Issue: -

## Description

Keys should be rotated on a regular basis to limit exposure if a given key should become compromised.

**Resolution**: Set key rotation period to `90` days.

## Examples

Example of **incorrect** code:

```terraform
resource "google_kms_key_ring" "keyring" {
  name     = "keyring-example"
  location = "global"
}

resource "google_kms_crypto_key" "example-key" {
  name            = "crypto-key-example"
  key_ring        = google_kms_key_ring.keyring.id
  rotation_period = "15552000s"

  lifecycle {
    prevent_destroy = true
  }
}
```

Example of **correct** code:

```terraform
resource "google_kms_key_ring" "keyring" {
  name     = "keyring-example"
  location = "global"
}

resource "google_kms_crypto_key" "example-key" {
  name            = "crypto-key-example"
  key_ring        = google_kms_key_ring.keyring.id
  rotation_period = "7776000s"

  lifecycle {
    prevent_destroy = true
  }
}
```