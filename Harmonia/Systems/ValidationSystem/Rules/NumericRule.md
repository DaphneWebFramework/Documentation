# NumericRule

Validates whether a given field contains a number or a numeric string.

By default, both native numbers (integers and floats) and string
representations of numbers (referred to as numeric) are valid. If the
optional parameter "strict" is provided, only native numbers are considered
valid.

## Methods

### Validate

Validates that the field contains a number or a numeric string.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: Optional parameter to specify validation mode. If set to "strict", the value must be a number. If omitted, both numbers and numeric strings are accepted.

#### Exceptions

- **\InvalidArgumentException**: If the parameter is neither "strict" nor `null`.
- **\RuntimeException**: If the parameter is "strict" and the value is not a number; or if no parameter is given and the value is not a number or numeric string; or if an invalid parameter is given.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
