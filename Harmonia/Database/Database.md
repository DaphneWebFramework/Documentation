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

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
