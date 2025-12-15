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

### Data

Returns the underlying data source.

#### Syntax

```php
public function Data(): array|object
```

#### Return Value

The data source being accessed, which can be an array or an object.

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

The field value if it exists.

#### Exceptions

- **\InvalidArgumentException**: If the field does not exist.

---

### GetFieldOrDefault

Retrieves the value of the specified field or returns a default if not
found.

Supports nested fields using dot notation (e.g., `'user.profile.name'`).

#### Syntax

```php
public function GetFieldOrDefault(string|int $field, mixed $defaultValue = null): mixed
```

#### Parameters

- **$field**: The field name or index to retrieve.
- **$defaultValue**: The default value to return if the field does not exist.

#### Return Value

The field value if it exists, otherwise the default value.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
