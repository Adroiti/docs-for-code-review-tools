Pattern: Disabled SSL peer verification

Issue: -

## Description

Make sure that `CURLOPT_SSL_VERIFYPEER` is not disabled, since that is a security issue.

## Further Reading

* [PHP_CodeSniffer - DrupalPractice.FunctionCalls.CurlSslVerifier](https://git.drupalcode.org/project/coder/-/tree/8.3.x/coder_sniffer/DrupalPractice/Sniffs/FunctionCalls/CurlSslVerifierSniff.php)