# SelectQuery

Class for building SQL SELECT queries.

## Methods

### Select

Specifies the columns to retrieve in the query.

#### Syntax

```php
public function Select(array<int,string> $columns): self
```

#### Parameters

- **$columns**: An array of column names or expressions. For example, `['column1', 'COUNT(*) AS count']`.

#### Return Value

The current instance.

---

### Where

Adds a WHERE clause to the query.

#### Syntax

```php
public function Where(string $condition, array<string,mixed> $substitutions = []): self
```

#### Parameters

- **$condition**: The WHERE condition. For example, `"id = :id AND name = :name"`.
- **$substitutions**: (Optional) Key-value pairs for placeholders in the condition.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If placeholders in the condition do not match substitutions.

---

### OrderBy

Adds an ORDER BY clause to the query.

#### Syntax

```php
public function OrderBy(array<int|string,string> $columns): self
```

#### Parameters

- **$columns**: Associative or indexed array of column names and their sorting direction. For example, `['column1' => 'ASC', 'column2' => 'DESC', 'column3']`.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If an invalid sorting direction is provided.

---

### Limit

Adds a LIMIT clause to the query.

#### Syntax

```php
public function Limit(int $limit, int|null $offset = null): self
```

#### Parameters

- **$limit**: The maximum number of rows to return.
- **$offset**: (Optional) The number of rows to skip before starting to return rows.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the limit or offset is negative.

---

### ToSql

Generates the SQL string representation of the query.

#### Syntax

```php
public function ToSql(): string
```

#### Return Value

The SQL query string.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
