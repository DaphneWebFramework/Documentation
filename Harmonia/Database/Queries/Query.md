# Query

Base class for SQL builders.

## Methods

### ToSql

Generates the SQL string representation of the query.

#### Syntax

```php
public final function ToSql(): string
```

#### Return Value

The SQL string.

#### Exceptions

- **\InvalidArgumentException**: If a placeholder in the SQL string has no matching binding, or if a binding is provided that does not match any placeholder.

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
