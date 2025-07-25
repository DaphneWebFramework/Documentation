# UpdateQuery

Class for building SQL queries to update data in a table.

#### Example

Updating the email and status of a specific user:

```php
$query = (new UpdateQuery)
    ->Table('users')
    ->Columns('email', 'status')
    ->Values(':email', ':status')
    ->Where('id = :id')
    ->Bind([
        'email'  => 'new.email@example.com',
        'status' => 'active',
        'id'     => 101
    ]);
```

**Generated SQL:**
```sql
UPDATE `users`
SET email = :email, status = :status
WHERE id = :id
```

## Methods

### Table

Defines the table where data will be updated.

#### Syntax

```php
public function Table(string $table): self
```

#### Parameters

- **$table**: The name of the table to update.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the table name is empty or contains only whitespace.

---

### Columns

Specifies the columns whose values will be updated.

#### Syntax

```php
public function Columns(string ...$columns): self
```

#### Parameters

- **$columns**: One or more column names that will have their values updated.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If no columns are provided or if any column is empty or contains only whitespace.

---

### Values

Defines the new values to be assigned to the specified columns.

#### Syntax

```php
public function Values(string ...$values): self
```

#### Parameters

- **$values**: One or more values to be assigned to the columns. These should be provided as strings or placeholders (e.g., `:email`, `:status`).

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If no values are provided, if any value is empty or contains only whitespace.

---

### Where

Filters the rows that should be updated.

#### Syntax

```php
public function Where(string $condition): self
```

#### Parameters

- **$condition**: A condition that specifies which rows should be updated.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the condition is empty or contains only whitespace.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
