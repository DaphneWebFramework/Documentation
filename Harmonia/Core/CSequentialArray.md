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

Inserts a new element before an existing element at a specified offset.

#### Syntax

```php
public function InsertBefore(int $offset, mixed $element): \Harmonia\Core\CSequentialArray
```

#### Parameters

- **$offset**: The zero-based offset before which the new element should be inserted.
- **$element**: The new element to insert.

#### Return Value

The current instance.

#### Exceptions

- **\OutOfRangeException**: If the offset is out of range.

---

### InsertAfter

Inserts a new element after an existing element at a specified offset.

#### Syntax

```php
public function InsertAfter(int $offset, mixed $element): \Harmonia\Core\CSequentialArray
```

#### Parameters

- **$offset**: The zero-based offset after which the new element should be inserted.
- **$element**: The new element to insert.

#### Return Value

The current instance.

#### Exceptions

- **\OutOfRangeException**: If the offset is out of range.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
