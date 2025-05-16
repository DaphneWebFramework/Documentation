# DatetimeRule

Validates whether a given field matches a specified datetime format.

## Methods

### Validate

Validates that the field matches a specified datetime format.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: The expected datetime format.

#### Exceptions

- **\RuntimeException**: If the value is not a string, the format is not a string, or the value does not match the format.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
