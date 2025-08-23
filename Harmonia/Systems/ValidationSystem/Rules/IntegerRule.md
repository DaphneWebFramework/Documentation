# IntegerRule

Validates whether a given field contains an integer or an integer-like
string.

By default, both native integers and string representations of integers
(often referred to as integer-like) are valid. If the optional parameter
'strict' is provided, only native integers are valid.

## Methods

### Validate

Validates that the field contains an integer or an integer-like string.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: Optional parameter to specify validation mode. If set to 'strict', the value must be an integer. If omitted, both integers and integer-like strings are accepted.

#### Exceptions

- **\RuntimeException**: If the parameter is 'strict' and the value is not an integer; or if no parameter is given and the value is not an integer or an integer-like string; or if an invalid parameter is given.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
