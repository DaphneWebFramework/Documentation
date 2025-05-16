# ResultSet

Represents a result set from a database query.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(?\Harmonia\Systems\DatabaseSystem\Proxies\MySQLiResult $result = null)
```

#### Parameters

- **$result**: (Optional) A result object, or `null` to represent an empty result set. Defaults to `null`.

---

### __destruct

Releases the memory associated with the result set.

#### Syntax

```php
public function __destruct()
```

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
public function Row(int $mode = self::ROW_MODE_ASSOCIATIVE): array<string,mixed>|array<int,mixed>|null
```

#### Parameters

- **$mode**: (Optional) Determines how keys in the returned array are indexed. Possible values are `ROW_MODE_ASSOCIATIVE` (default) for associative arrays and `ROW_MODE_NUMERIC` for numerically indexed arrays.

#### Return Value

An associative or indexed array representing the row, or `null` if the result set is empty or if the end of the result set has been reached.

#### Exceptions

- **\InvalidArgumentException**: If an invalid key mode is provided.

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
