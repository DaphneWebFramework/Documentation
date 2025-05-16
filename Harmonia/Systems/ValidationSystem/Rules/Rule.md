# Rule

Abstract base class for all validation rules.

## Methods

### __construct

Constructs a new instance with a reference to the native functions utility.

#### Syntax

```php
public function __construct(\Harmonia\Systems\ValidationSystem\NativeFunctions $nativeFunctions)
```

#### Parameters

- **$nativeFunctions**: The shared instance providing low-level validation utilities.

---

### Validate

Validates a field against the rule's logic.

#### Syntax

```php
public abstract function Validate(string|int $field, mixed $value, mixed $param): void
```

#### Parameters

- **$field**: The field name or index.
- **$value**: The field value to validate.
- **$param**: The optional parameter for validation.

#### Exceptions

- **\RuntimeException**: If validation fails.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
