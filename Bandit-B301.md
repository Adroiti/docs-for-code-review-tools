Pattern: Use of possibly insecure `pickle` module

Issue: -

## Description

`pickle` module appears to be in use, causing a possible security issue. It's not secure against erroneous or maliciously constructed data. It's recommended to never unpickle data received from an untrusted or unauthenticated source.

This rule checks for the following calls:

- `pickle.loads`
- `pickle.load`
- `pickle.Unpickler`
- `cPickle.loads`
- `cPickle.load`
- `cPickle.Unpickler`

## Further Reading

* [The Python Language Reference - pickle](https://docs.python.org/2/library/pickle.html)
* [OpenStack - B301: pickle](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b301-pickle)
