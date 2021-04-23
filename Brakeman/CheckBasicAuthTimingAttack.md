Pattern: Timing attack vulnerability for basic auth

Issue: -

## Description

The implementation of `http_basic_authenticate_with` did not use constant-time comparison when checking passwords, allowing timing attacks as described in CVE-2015-7576.

## Further Reading

* [NIST - CVE-2015-7576](https://nvd.nist.gov/vuln/detail/CVE-2015-7576)