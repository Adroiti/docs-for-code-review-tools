Pattern: Missing `tag` for custom element

Issue: -

## Description

No custom element `tag` option was specified. To automatically register a custom element, specify a name with a hyphen in it, e.g. `<svelte:options tag="my-thing"/>`. To hide this warning, use `<svelte:options tag={null}/>`.