# RegexRule

Validates whether a given field matches a specified regex pattern.

## Methods

### Validate

Validates that the field matches the specified regex pattern.

#### Syntax

```php
public function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index to validate.
- **$value**: The value of the field to validate.
- **$param**: The regex pattern to match against.

#### Exceptions

- **\RuntimeException**: If the value is not a string, the pattern is not a string, or the value does not match the pattern.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
