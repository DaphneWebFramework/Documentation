# DeleteQuery

Class for building SQL queries to delete data from a table.

#### Example

Deleting a user by ID:

```php
$query = (new DeleteQuery)
    ->Table('users')
    ->Where('id = :id')
    ->Bind(['id' => 101]);
```

**Generated SQL:**
```sql
DELETE FROM `users` WHERE id = :id
```

## Methods

### Table

Defines the table from which data will be deleted.

#### Syntax

```php
public function Table(string $table): self
```

#### Parameters

- **$table**: The name of the table from which rows will be deleted.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the table name is empty or contains only whitespace.

---

### Where

Filters the rows that should be deleted.

#### Syntax

```php
public function Where(string $condition): self
```

#### Parameters

- **$condition**: A condition that specifies which rows should be deleted.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the condition is empty or contains only whitespace.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
