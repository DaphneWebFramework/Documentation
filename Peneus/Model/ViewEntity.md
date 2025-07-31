# ViewEntity

Base class for entities that represent database views.

Subclasses must implement the `ViewDefinition` method, which provides a
SQL `SELECT` statement. These entities are automatically treated as views,
and are created using `CREATE OR REPLACE VIEW` when the `CreateTable` method
is invoked.

## Methods

### ViewDefinition

Returns the SQL `SELECT` statement that defines the view.

The returned SQL should not include a trailing semicolon (`;`), although
including one does not cause failure.

#### Syntax

```php
public static abstract function ViewDefinition(): string
```

#### Return Value

A `SELECT` query that defines the logical contents of the view.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
