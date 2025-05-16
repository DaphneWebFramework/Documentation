# CustomMetaRule

Provides functionality for user-defined validation rules represented as
closures.

## Methods

### __construct

Constructs a new instance with the provided closure.

#### Syntax

```php
public function __construct(\Closure $closure)
```

#### Parameters

- **$closure**: The closure function to be used for custom validation. The closure must accept a single parameter representing the field value and return `false` if the validation fails. Any other return value is considered a successful validation.

---

### GetName

Retrieves the name of the rule.

#### Syntax

```php
public function GetName(): string
```

#### Return Value

Always returns an empty string for custom rules.

---

### GetParam

Retrieves the parameter of the rule.

#### Syntax

```php
public function GetParam(): mixed
```

#### Return Value

Always returns `null` since custom rules do not have parameters.

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

- **\RuntimeException**: If the user-defined closure returns `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
