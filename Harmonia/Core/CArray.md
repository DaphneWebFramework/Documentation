# CArray

CArray is a wrapper for PHP's native `array` type, offering additional
methods for array manipulation and consistency in array operations.

## Methods

### __construct

Constructs a new instance of CArray.

#### Syntax

```php
public function __construct(array|\Harmonia\Core\CArray $value = [])
```

#### Parameters

- **$value**: (Optional) The array value to store. If omitted, defaults to an empty array. If a `CArray` instance is provided, the array value is copied from the original instance.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
