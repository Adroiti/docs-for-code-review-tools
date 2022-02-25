Pattern: Missing expiration for Azure Vault key

Issue: -

## Description

Expiration Date is an optional Key Vault Key behavior and is not set by default.

Set when the resource will be become inactive.

**Resolution**: Set an expiration date on the vault key.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_key_vault_key" "bad_example" {
  name         = "generated-certificate"
  key_vault_id = azurerm_key_vault.example.id
  key_type     = "RSA"
  key_size     = 2048

  key_opts = [
    "decrypt",
    "encrypt",
    "sign",
    "unwrapKey",
    "verify",
    "wrapKey",
  ]
}
```

Example of **correct** code:

```terraform
resource "azurerm_key_vault_key" "good_example" {
  name         = "generated-certificate"
  key_vault_id = azurerm_key_vault.example.id
  key_type     = "RSA"
  key_size     = 2048
  expiration_date = "1982-12-31T00:00:00Z"

  key_opts = [
    "decrypt",
    "encrypt",
    "sign",
    "unwrapKey",
    "verify",
    "wrapKey",
  ]
}
```