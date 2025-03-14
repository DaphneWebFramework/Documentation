# DataAccessor

Provides access to structured data, supporting nested field resolution.

## Methods

### __construct

Constructs a new instance with structured data.

#### Syntax

```php
public function __construct(array|object $data)
```

#### Parameters

- **$data**: The data to be accessed, either as an associative array or an object. If the data is an instance of `CArray`, it is converted to an array.

---

### HasField

Checks if the specified field exists in the data.

Supports nested fields using dot notation (e.g., `'user.profile.name'`).

#### Syntax

```php
public function HasField(string|int $field): bool
```

#### Parameters

- **$field**: The field name or index to check.

#### Return Value

Returns `true` if the field exists, `false` otherwise.

---

### GetField

Retrieves the value of the specified field.

Supports nested fields using dot notation (e.g., `'user.profile.name'`).

#### Syntax

```php
public function GetField(string|int $field): mixed
```

#### Parameters

- **$field**: The field name or index to retrieve.

#### Return Value

Returns the value of the field.

#### Exceptions

- **\RuntimeException**: If the field does not exist.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
