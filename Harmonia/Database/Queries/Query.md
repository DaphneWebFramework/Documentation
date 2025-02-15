# Query

Base class for SQL builders.

## Methods

### __construct

Creates a new instance.

#### Syntax

```php
public function __construct(string $tableName)
```

#### Parameters

- **$tableName**: The name of the table associated with the query.

---

### ToSql

Generates the SQL string representation of the query.

#### Syntax

```php
public final function ToSql(): string
```

#### Return Value

The SQL string.

#### Exceptions

- **\InvalidArgumentException**: If a placeholder is missing a binding or vice versa.

---

### Bindings

Retrieves the parameter bindings used in the query.

#### Syntax

```php
public function Bindings(): array<string,mixed>
```

#### Return Value

An associative array of bindings. For example, `['id' => 42, 'name' => 'John']`.

---

### Bind

Binds values to named placeholders.

#### Syntax

```php
public function Bind(array<string,mixed> $bindings): self
```

#### Parameters

- **$bindings**: An associative array where keys are placeholders (without `:` prefix) and values are their corresponding replacements.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If a binding key is invalid, or if a binding value is an array, a resource, or an object without a `__toString()` method.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
