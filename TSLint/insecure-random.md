Pattern: Use of insecure random source

Issue: -

## Description

Do not use insecure sources for random bytes. Use a secure random number
generator instead. Bans all uses of `Math.random` and
`crypto.pseudoRandomBytes`. Better alternatives are `crypto.randomBytes`
and `window.crypto.getRandomValues`. 

## Further Reading

* [TSLint - insecure-random](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)
* [CWE 330](https://cwe.mitre.org/data/definitions/330.html)
* [MDN Math.random](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random)
* [Node.js crypto.randomBytes()](https://nodejs.org/api/crypto.html#crypto_crypto_randombytes_size_callback)