Pattern: Malformed reactive component

Issue: -

## Description

`<${name}/>` will not be reactive if `${name}` changes. Use `<svelte:component this={${name}}/>` if you want this reactivity.