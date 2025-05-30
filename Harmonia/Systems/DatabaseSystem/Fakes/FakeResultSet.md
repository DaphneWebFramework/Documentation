# FakeResultSet

Represents a result set from a database query.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(array $rows = [])
```

#### Parameters

- **$rows**

---

### Columns

Retrieves the column names of the result set.

#### Syntax

```php
public function Columns(): string[]
```

#### Return Value

An array of column names. Returns an empty array if the result set is empty.

---

### RowCount

Retrieves the number of rows in the result set.

#### Syntax

```php
public function RowCount(): int
```

#### Return Value

The number of rows in the result set. Returns `0` if the result set is empty.

---

### Row

Retrieves a single row from the result set.

#### Syntax

```php
public function Row(int $mode = parent::ROW_MODE_ASSOCIATIVE): array<string,mixed>|array<int,mixed>|null
```

#### Parameters

- **$mode**: (Optional) Determines how keys in the returned array are indexed. Possible values are `ROW_MODE_ASSOCIATIVE` (default) for associative arrays and `ROW_MODE_NUMERIC` for numerically indexed arrays.

#### Return Value

An associative or indexed array representing the row, or `null` if the result set is empty or if the end of the result set has been reached.

---

### getIterator

Returns an iterator for traversing the result set row by row.

#### Syntax

```php
public function getIterator(): \Traversable
```

#### Return Value

An iterable object yielding rows as associative arrays.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
