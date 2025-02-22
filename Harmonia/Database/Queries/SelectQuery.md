# SelectQuery

Class for building SQL SELECT queries.

## Methods

### Columns

Specifies the columns to retrieve in the query.

If this method is not called, the query defaults to selecting
all columns (`*`).

#### Syntax

```php
public function Columns(string ...$columns): self
```

#### Parameters

- **$columns**: Column names or expressions to select. For example: `Columns('column1', 'COUNT(*) AS total')`.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If no columns are provided or if any column name is empty.

---

### From

Adds a FROM clause to the query.

#### Syntax

```php
public function From(string $tableName): self
```

#### Parameters

- **$tableName**: The name of the table.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the table name is empty.

---

### Where

Adds a WHERE clause to the query.

#### Syntax

```php
public function Where(string $condition): self
```

#### Parameters

- **$condition**: The WHERE condition.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the condition is empty.

---

### OrderBy

Adds an ORDER BY clause to the query.

#### Syntax

```php
public function OrderBy(string ...$columns): self
```

#### Parameters

- **$columns**: Column names and optional sorting directions, e.g., `OrderBy('column1 DESC', 'column2', 'column3 ASC')`.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If no columns are provided or if any column name is empty.

---

### Limit

Adds a LIMIT clause to the query.

#### Syntax

```php
public function Limit(int $limit, ?int $offset = null): self
```

#### Parameters

- **$limit**: The maximum number of rows to return.
- **$offset**: (Optional) The number of rows to skip before starting to return rows.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the limit or offset is negative.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
