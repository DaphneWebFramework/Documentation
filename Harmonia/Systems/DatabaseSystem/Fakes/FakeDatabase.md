# FakeDatabase

## Methods

### Expect

#### Syntax

```php
public function Expect(string $sql, array $bindings = [], array $result = [], int $lastInsertId = 0, int $lastAffectedRowCount = -1, ?int $times = self::UNLIMITED): void
```

#### Parameters

- **$sql**
- **$bindings**
- **$result**
- **$lastInsertId**
- **$lastAffectedRowCount**
- **$times**

---

### Execute

#### Syntax

```php
public function Execute(\Harmonia\Systems\DatabaseSystem\Queries\Query $query): ?\Harmonia\Systems\DatabaseSystem\Fakes\FakeResultSet
```

#### Parameters

- **$query**

---

### LastInsertId

#### Syntax

```php
public function LastInsertId(): int
```

---

### LastAffectedRowCount

#### Syntax

```php
public function LastAffectedRowCount(): int
```

---

### WithTransaction

#### Syntax

```php
public function WithTransaction(callable $callback): mixed
```

#### Parameters

- **$callback**

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
