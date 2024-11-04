# CSequentialArray

CSequentialArray is an extension of CArray designed specifically for
zero-based, sequentially indexed arrays.

## Methods

### PushBack

Adds an element to the end of the array.

#### Syntax

```php
public function PushBack(mixed $element): \Harmonia\Core\CSequentialArray
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
public function PushFront(mixed $element): \Harmonia\Core\CSequentialArray
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
public function InsertBefore(int $index, mixed $element): \Harmonia\Core\CSequentialArray
```

#### Parameters

- **$index**: The zero-based index before which the new element should be inserted.
- **$element**: The new element to insert.

#### Return Value

The current instance.

#### Exceptions

- **\OutOfRangeException**: If the index is out of range.

---

### InsertAfter

Inserts a new element after an existing element at a specified index.

#### Syntax

```php
public function InsertAfter(int $index, mixed $element): \Harmonia\Core\CSequentialArray
```

#### Parameters

- **$index**: The zero-based index after which the new element should be inserted.
- **$element**: The new element to insert.

#### Return Value

The current instance.

#### Exceptions

- **\OutOfRangeException**: If the index is out of range.

---

### Delete

Removes an element at the specified index.

The `$index` parameter accepts both integer and string types to ensure
signature compatibility with the base class `CArray`, allowing this
method to override `CArray::Delete`. However, if a string is given, an
exception is thrown, as `CSequentialArray` is intended for integer-based
indexing only.

#### Syntax

```php
public function Delete(int|string $index): \Harmonia\Core\CSequentialArray
```

#### Parameters

- **$index**: The zero-based index of the element to remove. If a string is given, an exception is thrown.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the index is a string.
- **\OutOfRangeException**: If the index is out of range.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
