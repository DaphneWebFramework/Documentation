# SelectQuery

Class for building SQL queries to retrieve data from a table.

#### Example

Fetching active users who registered after a specific date, sorted by their last login:

```php
$query = (new SelectQuery)
    ->Table('users')
    ->Columns('name', 'email', 'COUNT(*) AS loginCount')
    ->Where('status = :status AND createdAt >= :startDate')
    ->OrderBy(
        'lastLogin DESC',
        'name'
    )
    ->Limit(20, 10)
    ->Bind([
        'status'    => 'active',
        'startDate' => '2025-01-01'
    ]);
```

**Generated SQL:**
```sql
SELECT name, email, COUNT(*) AS loginCount FROM users
WHERE status = :status AND createdAt >= :startDate
ORDER BY lastLogin DESC, name
LIMIT 20 OFFSET 10
```

## Methods

### Table

Defines the table from which data will be selected.

#### Syntax

```php
public function Table(string $table): self
```

#### Parameters

- **$table**: The name of the table from which data will be retrieved.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the table name is empty or contains only whitespace.

---

### Columns

Specifies which columns should be retrieved in the query.

If this method is not called, the query defaults to selecting
all columns (`*`).

#### Syntax

```php
public function Columns(string ...$columns): self
```

#### Parameters

- **$columns**: One or more column names or expressions to retrieve.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If no columns are provided or if any column is empty or contains only whitespace.

---

### Where

Filters the query results based on a condition.

#### Syntax

```php
public function Where(string $condition): self
```

#### Parameters

- **$condition**: A condition used to filter the query results.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the condition is empty or contains only whitespace.

---

### OrderBy

Sorts the query results based on one or more columns.

#### Syntax

```php
public function OrderBy(string ...$columns): self
```

#### Parameters

- **$columns**: One or more column names, each optionally followed by a sorting direction (`ASC` or `DESC`).

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If no columns are provided or if any column is empty or contains only whitespace.

---

### Limit

Restricts the number of rows returned by the query.

#### Syntax

```php
public function Limit(int $limit, ?int $offset = null): self
```

#### Parameters

- **$limit**: The maximum number of rows to return.
- **$offset**: (Optional) The number of rows to skip before returning results. If `null`, no offset is applied.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the limit or offset is negative.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
