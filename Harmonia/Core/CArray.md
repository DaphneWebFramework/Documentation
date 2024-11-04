# CArray

CArray is a wrapper for PHP's native `array` type, offering additional
methods for array manipulation and consistency in array operations.

## Methods

### __construct

Constructs a new instance of CArray.

#### Syntax

```php
public function __construct(array|\Harmonia\Core\CArray $value = [])
```

#### Parameters

- **$value**: (Optional) The array value to store. If omitted, defaults to an empty array. If a `CArray` instance is provided, the array value is copied from the original instance.

---

### ContainsKey

Checks if the specified key exists in the array.

#### Syntax

```php
public function ContainsKey(string|int $key): bool
```

#### Parameters

- **$key**: The key to check for existence within the array.

#### Return Value

Returns `true` if the key exists in the array, `false` otherwise.

---

### ValueOrDefault

Returns the value at the specified key, or a default value if the key
does not exist in the array.

#### Syntax

```php
public function ValueOrDefault(string|int $key, mixed $defaultValue = null): mixed
```

#### Parameters

- **$key**: The key to look up in the array.
- **$defaultValue**: (Optional) The value to return if the key does not exist. Defaults to `null`.

#### Return Value

The value at the specified key if it exists, or the default value if the key is not found.

---

### PushBack

Adds an element to the end of the array.

#### Syntax

```php
public function PushBack(mixed $element): \Harmonia\Core\CArray
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
public function PushFront(mixed $element): \Harmonia\Core\CArray
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

> This method is intended for use with sequentially indexed arrays.
After insertion, the array is reindexed to maintain sequential order.
If applied to associative arrays, existing string keys are preserved, and
the new element is added with the next available zero-based integer key.

#### Syntax

```php
public function InsertBefore(int $offset, mixed $element): \Harmonia\Core\CArray
```

#### Parameters

- **$offset**: The zero-based offset before which the new element should be inserted.
- **$element**: The new element to insert.

#### Return Value

The current instance.

#### Exceptions

- **\OutOfRangeException**: If the offset is out of range.

#### See Also

- [`InsertAfter`](#InsertAfter)

---

### InsertAfter

Inserts a new element after an existing element at a specified offset.

> This method is intended for use with sequentially indexed arrays.
After insertion, the array is reindexed to maintain sequential order.
If applied to associative arrays, existing string keys are preserved, and
the new element is added with the next available zero-based integer key.

#### Syntax

```php
public function InsertAfter(int $offset, mixed $element): \Harmonia\Core\CArray
```

#### Parameters

- **$offset**: The zero-based offset after which the new element should be inserted.
- **$element**: The new element to insert.

#### Return Value

The current instance.

#### Exceptions

- **\OutOfRangeException**: If the offset is out of range.

#### See Also

- [`InsertBefore`](#InsertBefore)

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
