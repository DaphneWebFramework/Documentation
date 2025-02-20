# MySQLiHandle

## Methods

### __construct

#### Syntax

```php
public function __construct(\mysqli $object)
```

#### Parameters

- **$object**

---

### prepare

#### Syntax

```php
public function prepare(string $query): \Harmonia\Database\Proxies\MySQLiStatement|false
```

#### Parameters

- **$query**

---

### execute_query

#### Syntax

```php
public function execute_query(string $query, ?array $params): \Harmonia\Database\Proxies\MySQLiResult|bool
```

#### Parameters

- **$query**
- **$params**

---

### __call

#### Syntax

```php
public function __call(string $name, array $arguments): mixed
```

#### Parameters

- **$name**
- **$arguments**

---

### __get

#### Syntax

```php
public function __get(string $name): mixed
```

#### Parameters

- **$name**

---

### __set

#### Syntax

```php
public function __set(string $name, mixed $value): void
```

#### Parameters

- **$name**
- **$value**

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
