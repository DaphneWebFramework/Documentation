# StandardMetaRule

Represents a standard validation rule with an optional parameter.

## Methods

### __construct

Constructs a new instance with the provided rule name and parameter.

#### Syntax

```php
public function __construct(string $name, mixed $param, ?string $customMessage = null)
```

#### Parameters

- **$name**: The name of the rule.
- **$param**: The parameter for the rule.
- **$customMessage**: (Optional) A custom message to override the default message.

---

### GetName

Retrieves the name of the rule.

#### Syntax

```php
public function GetName(): string
```

#### Return Value

The name of the rule.

---

### GetParam

Retrieves the parameter of the rule.

#### Syntax

```php
public function GetParam(): mixed
```

#### Return Value

The parameter of the rule, or `null` if no parameter exists.

---

### Validate

Validates a given field against the rule.

#### Syntax

```php
public function Validate(string|int $field, mixed $value): void
```

#### Parameters

- **$field**: The name or index of the field to validate.
- **$value**: The value of the field to validate.

#### Exceptions

- **\RuntimeException**: If the rule does not exist or validation fails.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
