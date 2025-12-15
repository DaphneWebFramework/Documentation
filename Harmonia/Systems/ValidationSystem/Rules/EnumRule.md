# EnumRule

Validates whether a given field's value corresponds to a valid case of the
specified enum class.

Supports both backed enums and pure enums.

## Methods

### Validate

Validates that the field's value is a valid enum case of the specified
class.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: The fully qualified name of the enum class.

#### Exceptions

- **\InvalidArgumentException**: If the parameter is not a string.
- **\RuntimeException**: If the parameter is not a valid class name, or the value is not valid for the enum.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
