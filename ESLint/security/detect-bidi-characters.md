Pattern: Dangerous unicode bidi character

Issue: -

## Description

Detects cases of [trojan source attacks](https://trojansource.codes) that employ unicode bidi attacks to inject malicious code

## Examples 

Take the following code where `RLO`, `LRI`, `PDI`, `IRI` are placeholders to visualise the respective dangerous unicode characters:

```js
#!/usr/bin/env node

var accessLevel = 'user';

if (accessLevel != 'userRLO LRI// Check if adminPDI IRI') {
  console.log('You are an admin.');
}
```

The code above, will be rendered by a text editor as follows:

```js
#!/usr/bin/env node

var accessLevel = 'user';

if (accessLevel != 'user') {
  // Check if admin
  console.log('You are an admin.');
}
```

By looking at the rendered code above, a user reviewing this code might not notice the injected malicious unicode characters which are actually changing the semantic and the behaviour of the actual code.