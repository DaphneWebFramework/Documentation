# DatetimeRule

Validates whether a given field contains a datetime string.

If a format string is provided as the optional parameter, the value must
match that format exactly (per `DateTime::createFromFormat`). If no format
is provided, any string that PHP can parse into a datetime is accepted.

## Methods

### Validate

Validates that the field contains a datetime string.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: Optional format string. When provided, the value must match it exactly. When omitted, any PHP-parsable datetime string is accepted.

#### Exceptions

- **\InvalidArgumentException**: If the parameter is neither a string nor `null`.
- **\RuntimeException**: If a format is provided and the value does not match it exactly; or if no format is provided and the value is not a valid datetime string; or if an invalid parameter is given.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
