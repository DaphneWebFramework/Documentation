# DashboardRegistry

A registry that stores application-specific entity class names and their
validation rules, enabling the Management API to operate on them.

## Methods

### Register

Registers an entity class along with its validation rules.

#### Syntax

```php
public function Register(class-string $entityClass, array<string,mixed> $validationRules): void
```

#### Parameters

- **$entityClass**: The fully qualified class name of the entity.
- **$validationRules**: The validation rule set for creating a new record of the entity.

#### Exceptions

- **\InvalidArgumentException**: If the entity class is not a subclass of `Entity`.

---

### EntityClassFor

Returns the fully qualified class name of the entity that matches the
provided table name.

#### Syntax

```php
public function EntityClassFor(string $tableName): ?string
```

#### Parameters

- **$tableName**: The name of the table to resolve to an entity class.

#### Return Value

Fully qualified entity class name if found, otherwise `null`.

---

### ValidationRulesFor

Returns the validation rule set of the entity that matches the provided
table name.

#### Syntax

```php
public function ValidationRulesFor(string $tableName): ?array
```

#### Parameters

- **$tableName**: The name of the table to resolve to a validation rule set.

#### Return Value

The validation rule set if found, otherwise `null`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
