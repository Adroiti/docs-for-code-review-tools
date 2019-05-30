Pattern: Possible timing attack

Issue: -

## Description

Avoid timing attacks by not making direct string comparisons to
sensitive data. Do not compare against variables named password, secret,
api, apiKey, token, auth, pass, or hash.

## Further Reading

* [TSLint - possible-timing-attack](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)
* [Using Node.js Event Loop for Timing Attacks](https://snyk.io/blog/node-js-timing-attack-ccc-ctf)