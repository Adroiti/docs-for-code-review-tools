Pattern: Use of yaml load

Issue: -

## Description

This rule checks for the unsafe usage of the `yaml.load` function from
the PyYAML package. The yaml.load function provides the ability to construct
an arbitrary Python object, which may be dangerous if you receive a YAML
document from an untrusted source. The function yaml.safe_load limits this
ability to simple Python objects like integers or lists.

Please see <http://pyyaml.org/wiki/PyYAMLDocumentation#LoadingYAML> for more
information on `yaml.load` and yaml.safe_load

Example of **incorrect** code:

```python

>> Issue: [yaml_load] Use of unsafe yaml load. Allows instantiation of

arbitrary objects. Consider yaml.safe_load(). Severity: Medium Confidence:
High Location: examples/yaml_load.py:5

4 ystr = yaml.dump({'a' : 1, 'b' : 2, 'c' : 3}) 5 y = yaml.load(ystr) 6
yaml.dump(y)

```

## Further Reading

  - <http://pyyaml.org/wiki/PyYAMLDocumentation#LoadingYAML>
* [OpenStack - B506: yaml_load](https://docs.openstack.org/developer/bandit/plugins/yaml_load.html)
