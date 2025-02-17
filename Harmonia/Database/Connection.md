# Connection

Represents a connection to a MySQL server.

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

### SelectDatabase

Selects a database as the current database for the subsequent queries.

#### Syntax

```php
public function SelectDatabase(string $databaseName): void
```

#### Parameters

- **$databaseName**: The name of the database to select.

#### Exceptions

- **\RuntimeException**: If the database selection fails.

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
public function Execute(\Harmonia\Database\Queries\Query $query): ?\Harmonia\Database\Proxies\MySQLiResult
```

#### Parameters

- **$query**: The query object containing SQL and optionally its bindings.

#### Return Value

A `MySQLiResult` if the query produces a result set, `null` otherwise.

#### Exceptions

- **\RuntimeException**: If the query preparation or execution fails.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
