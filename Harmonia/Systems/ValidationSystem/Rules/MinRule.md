# MinRule

Validates whether a given field satisfies a specified minimum value.

## Methods

### Validate

Validates that the field contains a number meeting the specified minimum
value.

The specified minimum value is inclusive, meaning a value equal to
`$param` is valid.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: The minimum allowed value, inclusive.

#### Exceptions

- **\InvalidArgumentException**: If the parameter is not numeric.
- **\RuntimeException**: If the value is not numeric, the specified minimum is not numeric, or the value is less than the specified minimum.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
