Pattern: Empty `catch` comment

Issue: -

## Description

Checks for empty `catch` clause without a comment. It's rarely correct to do nothing in response to a caught exception. Typical responses are to handle it, log it, or if it is considered "impossible", rethrow it.

When it truly is appropriate to take no action whatsoever in a catch block, this rule enforces to have a comment to explain the reason this is justified.

## Example

Example of **incorrect** code:

``` php
public function saveFile($filename)
{
	$file = PhpFile::instance($filename);
	
	try {
		$file->lock();
	} catch (Exception $ex) {
	
	}
}
```

Example of **correct** code:

```php
public function saveFile($filename)
{
	$file = PhpFile::instance($filename);
	
	try {
		$file->lock();
	} catch (Exception $ex) {
		// Another process has locked the file; we will handle this in a bit.
	}
}
```

## Further Reading

* [Stack Overflow - What are the best practices for catching and re-throwing exceptions?](https://stackoverflow.com/questions/5551668/what-are-the-best-practices-for-catching-and-re-throwing-exceptions)
* [PHP_CodeSniffer - Squiz.Commenting.EmptyCatchComment](https://github.com/PHPCSStandards/PHP_CodeSniffer/blob/master/src/Standards/Squiz/Sniffs/Commenting/EmptyCatchCommentSniff.php)