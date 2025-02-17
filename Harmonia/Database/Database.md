# Database

Provides a central interface for working with databases.

This class manages connections and executes queries on the application
database. Connection details are retrieved from the configuration.

## Methods

### Execute

Executes a query on the active database.

This method executes the given query using the active connection. If the
query produces a result set (`SELECT`, `SHOW`, `DESCRIBE`, `EXPLAIN`),
it returns a `MySQLiResult` object. For queries that do not produce a
result set (`INSERT`, `UPDATE`, `DELETE`), it returns `null`. If the
connection is unavailable or execution fails, the error is logged and
`null` is returned.

#### Syntax

```php
public function Execute(\Harmonia\Database\Queries\Query $query): ?\Harmonia\Database\Proxies\MySQLiResult
```

#### Parameters

- **$query**: The query object containing SQL and optionally its bindings.

#### Return Value

A `MySQLiResult` if the query produces a result set, or `null` if the query does not produce a result set or if the execution fails.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
