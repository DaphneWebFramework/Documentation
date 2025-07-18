# Entity

Base class for Active Record entities.

This class provides common CRUD (Create, Read, Update, Delete) functionality
for database-backed objects. It supports automatic property mapping, database
persistence, and deletion.

Subclasses should define public properties that correspond to table columns.

## Methods

### __construct

Constructs an entity with the given data.

Date and time values in the provided data should be formatted as strings
(e.g., `'2025-03-15 12:45:00'`, `'2025-03-15'`). If a corresponding
property is an instance of `DateTime`, its value is updated using the
given string. Any conversion errors are silently ignored.

If a property assignment fails due to a type mismatch or other error,
it is silently skipped.

#### Syntax

```php
public function __construct(?array $data = null)
```

#### Parameters

- **$data**: (Optional) An associative array of property values. Keys must match the entity's public properties. If `id` is specified, it is also assigned.

---

### Populate

Populates the entity's properties with the given data.

Date and time values in the provided data should be formatted as strings
(e.g., `'2025-03-15 12:45:00'`, `'2025-03-15'`). If a corresponding
property is an instance of `DateTime`, its value is updated using the
given string. Any conversion errors are silently ignored.

If a property assignment fails due to a type mismatch or other error,
it is silently skipped.

#### Syntax

```php
public function Populate(array $data): void
```

#### Parameters

- **$data**: An associative array of property values. Keys must match the entity's public properties. If `id` is specified, it is also assigned.

---

### Save

Saves the entity to the database.

If `id` is `0`, a new record is inserted. Otherwise, an existing record
is updated.

#### Syntax

```php
public function Save(): bool
```

#### Return Value

Returns `true` on success, `false` on failure.

---

### Delete

Deletes the entity from the database.

On successful deletion, the `id` property is set to `0`.

#### Syntax

```php
public function Delete(): bool
```

#### Return Value

Returns `true` if the entity was successfully deleted. Returns `false` if `id` is `0` or if deletion fails.

---

### TableName

Returns the table name of the entity.

By default, the table name is derived from the entity's class name,
converted to lowercase. Subclasses can override this method to specify
a custom table name.

#### Example
```php
class CustomEntity extends Entity
{
    public static function TableName(): string
    {
        return 'custom_table_name';
    }
}
```

#### Syntax

```php
public static function TableName(): string
```

#### Return Value

The table name associated with the entity.

---

### Columns

Returns the column names associated with the entity.

The `id` column is always placed first, followed by all other public,
non-static, non-readonly properties whose values are considered bindable.
Bindable values exclude arrays, resources, and objects lacking a
`__toString()` method.

#### Syntax

```php
public static function Columns(): string[]
```

#### Return Value

An ordered list of column names.

---

### FindById

Retrieves an entity by its primary key.

#### Syntax

```php
public static function FindById(int $id): static|null
```

#### Parameters

- **$id**: The primary key of the entity to retrieve.

#### Return Value

An instance of the called class if a matching record is found, `null` otherwise.

---

### FindFirst

Retrieves the first entity that matches the given condition.

#### Syntax

```php
public static function FindFirst(?string $condition = null, ?array $bindings = null, ?string $orderBy = null): ?static
```

#### Parameters

- **$condition**: (Optional) A filtering expression that determines which entity to retrieve (e.g., `"status = :status"`). If `null` (default), no filtering is applied.
- **$bindings**: (Optional) An associative array of values to replace placeholders in the condition (e.g., `['status' => 'active']`). If `null` (default), no parameters are bound.
- **$orderBy**: (Optional) A sorting expression that determines which matching entity is returned first (e.g., `"createdAt DESC"`). If `null` (default), no ordering is applied.

#### Return Value

An instance of the called class if a matching record is found, `null` otherwise.

---

### Find

Retrieves all entities that match the given condition.

#### Syntax

```php
public static function Find(?string $condition = null, ?array $bindings = null, ?string $orderBy = null, ?int $limit = null, ?int $offset = null): array
```

#### Parameters

- **$condition**: (Optional) A filtering expression that determines which entities to retrieve (e.g., `"status = :status"`). If `null` (default), no filtering is applied.
- **$bindings**: (Optional) An associative array of values to replace placeholders in the condition (e.g., `['status' => 'active']`). If `null` (default), no parameters are bound.
- **$orderBy**: (Optional) A sorting expression that determines the order of the returned entities (e.g., `"createdAt DESC"`). If `null` (default), no ordering is applied.
- **$limit**: (Optional) The maximum number of entities to return. If `null` (default), all matching entities are returned.
- **$offset**: (Optional) The number of entities to skip before returning results. If `null` (default), no offset is applied.

#### Return Value

An array of instances of the called class.

---

### Count

Returns the number of rows in the associated table that match a condition.

#### Syntax

```php
public static function Count(?string $condition = null, ?array $bindings = null): int
```

#### Parameters

- **$condition**: (Optional) A filtering expression for rows to count (e.g., `"status = :status"`). If `null`, all rows are counted.
- **$bindings**: (Optional) An associative array of values to bind to placeholders in the condition (e.g., `['status' => 'active']`). If `null`, no bindings are applied.

#### Return Value

The number of matching rows. Returns `0` if the query fails.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
