Pattern: Key Vault Secret should have an expiration date set

Issue: -

## Description

Expiration Date is an optional Key Vault Secret behavior and is not set by default.

Set when the resource will be become inactive.

**Resolution**: Set an expiry for secrets.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_key_vault_secret" "bad_example" {
  name         = "secret-sauce"
  value        = "szechuan"
  key_vault_id = azurerm_key_vault.example.id
}
```

Example of **correct** code:

```terraform
resource "azurerm_key_vault_secret" "good_example" {
  name            = "secret-sauce"
  value           = "szechuan"
  key_vault_id    = azurerm_key_vault.example.id
  expiration_date = "1982-12-31T00:00:00Z"
}
```