# FakeResultSet

Simulates a database result set for testing purposes.

This class is used by `FakeDatabase` to simulate the result of a database
query without requiring a real database connection. It provides an in-memory
result stream that mimics the behavior of `ResultSet`.

## Methods

### __construct

Constructs a new instance with the given row data and initializes the
internal cursor.

#### Syntax

```php
public function __construct(array<int,array<string,mixed>> $rows = [])
```

#### Parameters

- **$rows**: (Optional) The list of result rows. Defaults to an empty list.

---

### Columns

Retrieves the column names from the first row.

#### Syntax

```php
public function Columns(): string[]
```

#### Return Value

An array of column names. Returns an empty array if no rows are defined.

---

### RowCount

Retrieves the number of rows.

#### Syntax

```php
public function RowCount(): int
```

#### Return Value

The number of rows. Returns `0` if no rows are defined.

---

### Row

Retrieves the current row and advances the internal cursor.

#### Syntax

```php
public function Row(int $mode = self::ROW_MODE_ASSOCIATIVE): array<string,mixed>|array<int,mixed>|null
```

#### Parameters

- **$mode**: (Optional) Row mode. Use `ROW_MODE_ASSOCIATIVE` (default) to return rows as associative arrays, or `ROW_MODE_NUMERIC` for numerically indexed arrays.

#### Return Value

The current row, or `null` if there are no more rows.

#### Exceptions

- **\InvalidArgumentException**: If an invalid row mode is provided.

---

### getIterator

Returns an iterator for traversing row by row.

#### Syntax

```php
public function getIterator(): \Traversable
```

#### Return Value

An iterable object yielding rows as associative arrays.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
