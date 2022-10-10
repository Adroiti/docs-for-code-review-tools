Pattern: Use of restricted package

Issue: -

## Description

Warns when importing black-listed packages.

## Configuration

Black-list of package names (or regular expression package names).

## Example:

```toml
[imports-blacklist]
  arguments =["crypto/md5", "crypto/sha1", "crypto/**/pkix"]
```

## Further Reading

* [Revive - imports-blacklist](https://revive.run/r#imports-blacklist)