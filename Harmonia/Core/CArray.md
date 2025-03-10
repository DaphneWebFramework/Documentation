# CArray

CArray is a wrapper for PHP's native `array` type, offering additional
methods for array manipulation and consistency in array operations.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(array|\Harmonia\Core\CArray $value = [])
```

#### Parameters

- **$value**: (Optional) The array value to store. If omitted, defaults to an empty array. If a `CArray` instance is provided, the array value is copied from the original instance.

---

### ToArray

Retrieves a copy of the array stored in the instance.

#### Syntax

```php
public function ToArray(): array
```

#### Return Value

A copy of the array stored in the instance.

---

### IsEmpty

Checks if the array is empty.

#### Syntax

```php
public function IsEmpty(): bool
```

#### Return Value

Returns `true` if the array is empty, `false` otherwise.

---

### Has

Checks if the specified key exists.

#### Syntax

```php
public function Has(string|int $key): bool
```

#### Parameters

- **$key**: The key to check for existence.

#### Return Value

Returns `true` if the key exists, `false` otherwise.

---

### Get

Returns the value at the specified key.

#### Syntax

```php
public function Get(string|int $key): mixed
```

#### Parameters

- **$key**: The key to look up.

#### Return Value

The value at the specified key if it exists, or `null` if the key is not found.

---

### GetOrDefault

Returns the value at the specified key, or a default value if the key
does not exist.

#### Syntax

```php
public function GetOrDefault(string|int $key, mixed $defaultValue): mixed
```

#### Parameters

- **$key**: The key to look up.
- **$defaultValue**: The value to return if the key does not exist.

#### Return Value

The value at the specified key if it exists, or the default value if the key is not found.

---

### Set

Adds or updates the value at the specified key.

#### Syntax

```php
public function Set(string|int $key, mixed $value): self
```

#### Parameters

- **$key**: The key at which to set the value.
- **$value**: The value to set at the specified key.

#### Return Value

The current instance.

---

### Remove

Removes an element by its key.

#### Syntax

```php
public function Remove(string|int $key): self
```

#### Parameters

- **$key**: The key of the element to remove.

#### Return Value

The current instance.

---

### Clear

Clears all elements from the array, making it empty.

#### Syntax

```php
public function Clear(): self
```

#### Return Value

The current instance.

---

### ApplyInPlace

Applies a function to the current value.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function ApplyInPlace(callable $function, mixed ...$args): self
```

#### Parameters

- **$function**: The function to apply to the current value. It must accept an array as its first parameter. Any additional arguments passed to this method will be forwarded to the applied function.
- **$args**: Additional arguments to pass to the applied function.

#### Return Value

The current instance.

#### Exceptions

- **\UnexpectedValueException**: If the applied function returns a value that is not an array.

#### See Also

- [`Apply`](#Apply)

---

### Apply

Applies a function to the current value.

#### Syntax

```php
public function Apply(callable $function, mixed ...$args): \Harmonia\Core\CArray
```

#### Parameters

- **$function**: The function to apply to the current value. It must accept an array as its first parameter. Any additional arguments passed to this method will be forwarded to the applied function.
- **$args**: Additional arguments to pass to the applied function.

#### Return Value

A new `CArray` instance containing the result of the applied function.

#### Exceptions

- **\UnexpectedValueException**: If the applied function returns a value that is not an array.

#### See Also

- [`ApplyInPlace`](#ApplyInPlace)

---

### offsetExists

Provides array-like access to check if a value exists at a given key.

#### Syntax

```php
public function offsetExists(mixed $offset): bool
```

#### Parameters

- **$offset**: The key to check for existence.

#### Return Value

Returns `true` if the key exists, `false` otherwise.

#### Exceptions

- **\TypeError**: If the key is not a string or integer.

---

### offsetGet

Provides array-like access to retrieve the value at a given key.

#### Syntax

```php
public function offsetGet(mixed $offset): mixed
```

#### Parameters

- **$offset**: The key to look up.

#### Return Value

The value at the specified key, or `null` if the key is not found.

#### Exceptions

- **\TypeError**: If the key is not a string or integer.

---

### offsetSet

Provides array-like access to set a value at a specified key.

#### Syntax

```php
public function offsetSet(mixed $offset, mixed $value): void
```

#### Parameters

- **$offset**: The key at which to set the value.
- **$value**: The value to set at the specified key.

#### Exceptions

- **\TypeError**: If the key is not a string or integer.

---

### offsetUnset

Provides array-like access to unset a value at a specified key.

#### Syntax

```php
public function offsetUnset(mixed $offset): void
```

#### Parameters

- **$offset**: The key of the element to unset.

#### Exceptions

- **\TypeError**: If the key is not a string or integer.

---

### count

Returns the number of elements.

Can be accessed interchangeably as `count($instance)`, `$instance->count()`,
or `$instance->Count()` due to PHP's case insensitivity and the `\Countable`
interface.

#### Syntax

```php
public function count(): int
```

#### Return Value

The number of elements.

---

### getIterator

Provides array-like traversal over each element.

#### Syntax

```php
public function getIterator(): \Traversable
```

#### Return Value

An iterator yielding each element.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
