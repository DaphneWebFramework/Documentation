# CSequentialArray

CSequentialArray is an extension of CArray designed specifically for
zero-based, sequentially indexed arrays.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(array|\Harmonia\Core\CArray $value = [])
```

#### Parameters

- **$value**: (Optional) The array value to store. If omitted, defaults to an empty array. If a `CArray` or `CSequentialArray` instance is provided, its array value is copied. Only arrays with sequential, zero-based integer indexes are accepted.

#### Exceptions

- **\InvalidArgumentException**: If the provided array is non-sequential, not zero-based, or contains non-integer indexes.

---

### Has

Checks if the specified index exists.

The `$index` parameter accepts both strings and integers to comply with
the `CArray::Has` signature. However, if a string is provided, an
exception is thrown because `CSequentialArray` only supports integer
indexing.

#### Syntax

```php
public function Has(string|int $index): bool
```

#### Parameters

- **$index**: The index to check for existence. If a string is given, an exception is thrown.

#### Return Value

Returns `true` if the index is within range, `false` otherwise.

#### Exceptions

- **\InvalidArgumentException**: If the index is a string.

---

### Get

Returns the value at the specified index.

The `$index` parameter accepts both strings and integers to comply with
the `CArray::Get` signature. However, if a string is provided, an
exception is thrown because `CSequentialArray` only supports integer
indexing.

#### Syntax

```php
public function Get(string|int $index): mixed
```

#### Parameters

- **$index**: The zero-based index to look up. If a string is given, an exception is thrown.

#### Return Value

The value at the specified index if it exists, or `null` if the index is out of range.

#### Exceptions

- **\InvalidArgumentException**: If the index is a string.

---

### GetOrDefault

Returns the value at the specified index, or a default value if the
index does not exist.

The `$index` parameter accepts both strings and integers to comply with
the `CArray::GetOrDefault` signature. However, if a string is provided,
an exception is thrown because `CSequentialArray` only supports integer
indexing.

#### Syntax

```php
public function GetOrDefault(string|int $index, mixed $defaultValue): mixed
```

#### Parameters

- **$index**: The zero-based index to look up. If a string is given, an exception is thrown.
- **$defaultValue**: The value to return if the index does not exist.

#### Return Value

The value at the specified index if it exists, or the default value if the index is out of range.

#### Exceptions

- **\InvalidArgumentException**: If the index is a string.

---

### Set

Updates the value at the specified index.

The `$index` parameter accepts both strings and integers to comply with
the `CArray::Set` signature. However, if a string is provided, an
exception is thrown because `CSequentialArray` only supports integer
indexing.

#### Syntax

```php
public function Set(string|int $index, mixed $value): self
```

#### Parameters

- **$index**: The zero-based index at which to set the value. If a string is given, an exception is thrown. If the index is out of range, no changes are made.
- **$value**: The value to set at the specified index.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the index is a string.

---

### Delete

Removes an element at the specified index.

The `$index` parameter accepts both strings and integers to comply with
the `CArray::Delete` signature. However, if a string is provided, an
exception is thrown because `CSequentialArray` only supports integer
indexing.

#### Syntax

```php
public function Delete(string|int $index): self
```

#### Parameters

- **$index**: The zero-based index of the element to remove. If a string is given, an exception is thrown. If the index is out of range, no changes are made.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the index is a string.

---

### PushBack

Adds an element to the end of the array.

#### Syntax

```php
public function PushBack(mixed $element): self
```

#### Parameters

- **$element**: The element to add to the array.

#### Return Value

The current instance.

---

### PushFront

Adds an element to the beginning of the array.

#### Syntax

```php
public function PushFront(mixed $element): self
```

#### Parameters

- **$element**: The element to add to the array.

#### Return Value

The current instance.

---

### PopBack

Removes and returns the last element of the array.

#### Syntax

```php
public function PopBack(): mixed
```

#### Return Value

The last element, or `null` if the array is empty.

---

### PopFront

Removes and returns the first element of the array.

#### Syntax

```php
public function PopFront(): mixed
```

#### Return Value

The first element, or `null` if the array is empty.

---

### InsertBefore

Inserts a new element before an existing element at a specified index.

#### Syntax

```php
public function InsertBefore(int $index, mixed $element): self
```

#### Parameters

- **$index**: The zero-based index before which the new element should be inserted. If the index is out of range, no changes are made.
- **$element**: The new element to insert.

#### Return Value

The current instance.

---

### InsertAfter

Inserts a new element after an existing element at a specified index.

#### Syntax

```php
public function InsertAfter(int $index, mixed $element): self
```

#### Parameters

- **$index**: The zero-based index after which the new element should be inserted. If the index is out of range, no changes are made.
- **$element**: The new element to insert.

#### Return Value

The current instance.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
