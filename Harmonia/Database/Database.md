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

A `ResultSet` object, or `null` if the connection is unavailable or execution fails.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
