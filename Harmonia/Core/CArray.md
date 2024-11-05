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

Checks if the specified key exists in the array.

#### Syntax

```php
public function Has(string|int $key): bool
```

#### Parameters

- **$key**: The key to check for existence within the array.

#### Return Value

Returns `true` if the key exists in the array, `false` otherwise.

---

### Get

Returns the value at the specified key, or a default value if the key
does not exist in the array.

#### Syntax

```php
public function Get(string|int $key, mixed $defaultValue = null): mixed
```

#### Parameters

- **$key**: The key to look up in the array.
- **$defaultValue**: (Optional) The value to return if the key does not exist. Defaults to `null`.

#### Return Value

The value at the specified key if it exists, or the default value if the key is not found.

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

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
