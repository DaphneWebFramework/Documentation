# Connection

## Methods

### __construct

Opens a connection to a MySQL server.

#### Syntax

```php
public function __construct(string $hostname, string $username, string $password, ?string $charset = null)
```

#### Parameters

- **$hostname**: The host name or IP address of the MySQL server.
- **$username**: The username for the MySQL authentication.
- **$password**: The password for the MySQL authentication.
- **$charset**: (Optional) The character set to use for the connection.

#### Exceptions

- **\RuntimeException**: If the connection to the MySQL server fails or if the character set cannot be set.

---

### __destruct

Closes the connection to the MySQL server.

#### Syntax

```php
public function __destruct()
```

---

### Execute

Executes a query on the MySQL server.

This method prepares and executes the given query. If the query produces
a result set (such as `SELECT`, `SHOW`, `DESCRIBE`, or `EXPLAIN`), it
returns a `MySQLiResult` object. For queries that do not produce a result
set (such as `INSERT`, `UPDATE`, or `DELETE`), it returns `null`. Any
execution failure results in an exception.

#### Syntax

```php
public function Execute(\Harmonia\Database\Queries\Query $query): ?\Harmonia\Database\MySQLiResult
```

#### Parameters

- **$query**: The query object containing SQL and optionally its bindings.

#### Return Value

A `MySQLiResult` if the query produces a result set, `null` otherwise.

#### Exceptions

- **\RuntimeException**: If the query preparation or execution fails.

---

### transformQuery

Converts a query with named placeholders into MySQLi-compatible format.

This method replaces named placeholders (e.g., `:id`, `:name`) with `?`
for MySQLi `prepare()`, reorders binding values to match their appearance
in the query, and generates a type string for `bind_param()`.

#### Syntax

```php
public function transformQuery(\Harmonia\Database\Queries\Query $query): \stdClass
```

#### Parameters

- **$query**: The query object containing SQL and its bindings.

#### Return Value

Returns an object with three properties: `sql`, which is the transformed SQL query with `?` placeholders for `prepare()`; `values`, which is an indexed array of ordered binding values for `bind_param()`; and `types`, which is a string representing the parameter types for `bind_param()` (e.g., `"isd"`).

#### Exceptions

- **\InvalidArgumentException**: If a placeholder in the SQL string has no matching binding, or if a binding is provided that does not match any placeholder.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
