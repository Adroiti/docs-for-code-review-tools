Pattern: Wrong attributes order

Issue: -

## Description

Requires order of attributes. When more attributes are in one `#[]`, e.g. `#[One, Two]`, the first attribute name is used to resolve the order.

This rule provides the following settings:

* `order`: required order of attributes. Supports prefixes, eg. `ORM\`, and mask , eg. `AppAssert*`.
* `orderAlphabetically`: order attributes alphabetically. Boolean value, default `false`.

Only one order can be set.

```xml
<rule ref="SlevomatCodingStandard.Attributes.AttributesOrder">
	<properties>
		<property name="order" type="array">
			<element value="ORM\Table"/>
			<element value="ORM\"/>
			<element value="One"/>
			<element value="Two"/>
		</property>
	</properties>
</rule>
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Attributes.AttributesOrder](https://github.com/slevomat/coding-standard/blob/master/doc/attributes.md#slevomatcodingstandardattributesattributesorder-)