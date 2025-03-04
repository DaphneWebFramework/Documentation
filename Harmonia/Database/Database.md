# Database

Provides a central interface for working with databases.

This class manages connections and executes queries on the application
database. Connection details are retrieved from the configuration.

## Methods

### Execute

Executes a query on the database.

#### Syntax

```php
public function Execute(\Harmonia\Database\Queries\Query $query): ?\Harmonia\Database\Proxies\MySQLiResult
```

#### Parameters

- **$query**: The query object containing SQL and optionally its bindings.

#### Return Value

A `ResultSet` object, or `null` if a connection to the database server cannot be established or execution fails.

---

### LastInsertId

Retrieves the last inserted row's ID.

#### Syntax

```php
public function LastInsertId(): int
```

#### Return Value

The last inserted row's ID. The method returns `0` if the connection to the database server cannot be established or if the last query was not an `INSERT` or no `AUTO_INCREMENT` value was generated.

---

### LastAffectedRowCount

Retrieves the number of rows affected by the last query.

#### Syntax

```php
public function LastAffectedRowCount(): int
```

#### Return Value

The number of rows affected by the last modifying query. Returns `0` if no rows were affected. Returns `-1` if the connection to the database server cannot be established or the last query has failed.

---

### WithTransaction

Executes a callable within a database transaction.

This method initiates a transaction, executes the provided callback, and
commits the transaction if no exception is thrown. The return value of
the callback is then propagated as the result of the transaction. A
callback returning any value (including `false`) is considered a valid
outcome and will be returned after a successful commit. If an exception
occurs during execution or commit, the transaction is rolled back and
`false` is returned.

#### Syntax

```php
public function WithTransaction(callable $callback): mixed
```

#### Parameters

- **$callback**: The callback function to execute within the transaction. It may return any value representing a valid business logic outcome, or throw an exception to signal an error.

#### Return Value

Returns the value from the callback if the transaction is committed successfully. Returns `false` if the connection is unavailable or if an exception occurs during the transaction.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
