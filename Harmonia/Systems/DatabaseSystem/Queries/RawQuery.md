# RawQuery

Represents a predefined SQL query with optional bindings.

#### Examples

```php
$query = (new RawQuery)
    ->Sql('DROP TABLE IF EXISTS `users_temp`');
```

```php
$query = (new RawQuery)
    ->Sql('SHOW FULL TABLES FROM `mydb` LIKE :pattern')
    ->Bind(['pattern' => 'user_%']);
```

## Methods

### Sql

Sets the SQL string.

#### Syntax

```php
public function Sql(string $sql): self
```

#### Parameters

- **$sql**: The SQL string. May include named placeholders (e.g., `:name`).

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the SQL string is empty or contains only whitespace.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
