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

### Has

Checks if the specified key exists.

#### Syntax

```php
public function Has(string|int $key): bool
```

#### Parameters

- **$key**: The key to check for existence within the array.

#### Return Value

Returns `true` if the key exists, `false` otherwise.

---

### Get

Returns the value at the specified key, or a default value if the key
does not exist.

#### Syntax

```php
public function Get(string|int $key, mixed $defaultValue = null): mixed
```

#### Parameters

- **$key**: The key to look up.
- **$defaultValue**: (Optional) The value to return if the key does not exist. Defaults to `null`.

#### Return Value

The value at the specified key if it exists, or the default value if the key is not found.

---

### Set

Adds or updates the value at the specified key.

#### Syntax

```php
public function Set(string|int $key, mixed $value): \Harmonia\Core\CArray
```

#### Parameters

- **$key**: The key at which to set the value.
- **$value**: The value to set at the specified key.

#### Return Value

The current instance.

---

### Delete

Removes an element by its key.

#### Syntax

```php
public function Delete(string|int $key): \Harmonia\Core\CArray
```

#### Parameters

- **$key**: The key of the element to remove.

#### Return Value

The current instance.

---

### offsetExists

Checks if the specified offset exists.

#### Syntax

```php
public function offsetExists(mixed $offset): bool
```

#### Parameters

- **$offset**: The offset to check for existence within the array.

#### Return Value

Returns `true` if the offset exists, `false` otherwise.

#### Exceptions

- **\TypeError**: If the offset is not a string or integer.

---

### offsetGet

Returns the value at the specified offset.

#### Syntax

```php
public function offsetGet(mixed $offset): mixed
```

#### Parameters

- **$offset**: The offset to look up.

#### Return Value

The value at the specified offset, or `null` if the offset is not found.

#### Exceptions

- **\TypeError**: If the offset is not a string or integer.

---

### offsetSet

Sets the value at the specified offset.

#### Syntax

```php
public function offsetSet(mixed $offset, mixed $value): void
```

#### Parameters

- **$offset**: The offset at which to set the value.
- **$value**: The value to set at the specified offset.

#### Exceptions

- **\TypeError**: If the offset is not a string or integer.

---

### offsetUnset

Unsets the value at the specified offset.

#### Syntax

```php
public function offsetUnset(mixed $offset): void
```

#### Parameters

- **$offset**: The offset of the element to unset.

#### Exceptions

- **\TypeError**: If the offset is not a string or integer.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
