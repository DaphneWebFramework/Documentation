# MaxlengthRule

Validates whether a given field satisfies a specified maximum length.

## Methods

### Validate

Validates that the field contains a string not exceeding the specified
maximum length.

The specified maximum length is inclusive, meaning a string with exactly
`$param` characters is valid.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: The maximum allowed length, inclusive.

#### Exceptions

- **\RuntimeException**: If the value is not a string, the specified length is not an integer-like value, or the value exceeds the specified length.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
