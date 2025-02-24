# InsertQuery

Class for building SQL queries to insert data into a table.

#### Example

Inserting a new user with specified columns and values:

```php
$query = (new InsertQuery)
    ->Into('users')
    ->Columns('id', 'name', 'email', 'status', 'createdAt')
    ->Values(':id', ':name', ':email', ':status', ':createdAt')
    ->Bind([
        'id'        => 101,
        'name'      => 'John Doe',
        'email'     => 'john.doe@example.com',
        'status'    => 'active',
        'createdAt' => '2025-02-23 15:30:00'
    ]);
```

**Generated SQL:**
```sql
INSERT INTO users (id, name, email, status, createdAt)
VALUES (:id, :name, :email, :status, :createdAt)
```

## Methods

### Into

Defines the table where data will be inserted.

#### Syntax

```php
public function Into(string $table): self
```

#### Parameters

- **$table**: The name of the table where data will be inserted.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the table name is empty or contains only whitespace.

---

### Columns

Specifies the columns into which data will be inserted.

#### Syntax

```php
public function Columns(string ...$columns): self
```

#### Parameters

- **$columns**: One or more column names where data will be inserted.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If no columns are provided or if any column is empty or contains only whitespace.

---

### Values

Specifies the values to be inserted into the table.

#### Syntax

```php
public function Values(string ...$values): self
```

#### Parameters

- **$values**: One or more values to insert. These should be provided as strings or placeholders (e.g., `:id`, `:name`).

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If no values are provided or if any value is empty or contains only whitespace.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
