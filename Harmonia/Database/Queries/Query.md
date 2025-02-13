# Query

Base class for SQL query builders.

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
public abstract function ToSql(): string
```

#### Return Value

The SQL query string.

---

### Substitutions

Retrieves the parameter substitutions used in the query.

#### Syntax

```php
public function Substitutions(): array
```

#### Return Value

An associative array of substitutions.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
