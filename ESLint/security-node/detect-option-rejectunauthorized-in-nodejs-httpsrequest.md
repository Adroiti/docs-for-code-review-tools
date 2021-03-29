Pattern: Use of `rejectUnauthorized:false` for Node.js

Issue: -

## Description

Detect `rejectUnauthorized:false` in Node.js https request method. By setting `rejectUnauthorized: false`, you're saying "I don't care if I can't verify the server's identity." This is not a good solution as it leaves you vulnerable to MITM attacks.

A better solution for self-signed certificates is to set the appropriate `ca` value to your custom CA when connecting client-side. Also, make sure your `host` value matches that of the Common Name of the server's self-signed certificate. For example:

```js
var socket = tls.connect({
  host: 'MyTLSServer',
  port: 1337,
  ca: [ fs.readFileSync('CA.pem') ],
}, function() {
  // Connected!
});
```