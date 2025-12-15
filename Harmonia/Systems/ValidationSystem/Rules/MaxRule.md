# MaxRule

Validates whether a given field satisfies a specified maximum value.

## Methods

### Validate

Validates that the field contains a number not exceeding the specified
maximum value.

The specified maximum value is inclusive, meaning a value equal to
`$param` is valid.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: The maximum allowed value, inclusive.

#### Exceptions

- **\InvalidArgumentException**: If the parameter is not numeric.
- **\RuntimeException**: If the value is not numeric, the specified maximum is not numeric, or the value exceeds the specified maximum.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
