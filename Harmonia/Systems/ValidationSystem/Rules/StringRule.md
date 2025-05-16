# StringRule

Validates whether a given field is a string.

## Methods

### Validate

Validates that the field contains a string.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: Unused in this rule.

#### Exceptions

- **\RuntimeException**: If the value is not a string.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
