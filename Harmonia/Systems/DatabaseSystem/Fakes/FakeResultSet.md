# FakeResultSet

## Methods

### __construct

#### Syntax

```php
public function __construct(array $rows = [])
```

#### Parameters

- **$rows**

---

### Columns

#### Syntax

```php
public function Columns(): array
```

---

### RowCount

#### Syntax

```php
public function RowCount(): int
```

---

### Row

#### Syntax

```php
public function Row(int $mode = ResultSet::ROW_MODE_ASSOCIATIVE): ?array
```

#### Parameters

- **$mode**

---

### getIterator

#### Syntax

```php
public function getIterator(): \Traversable
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
