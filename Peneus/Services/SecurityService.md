# SecurityService

## Methods

### HashPassword

#### Syntax

```php
public function HashPassword(string $password): string
```

#### Parameters

- **$password**

---

### VerifyPassword

#### Syntax

```php
public function VerifyPassword(string $password, string $hash): bool
```

#### Parameters

- **$password**
- **$hash**

---

### GenerateToken

#### Syntax

```php
public function GenerateToken(): string
```

---

### GenerateCsrfToken

#### Syntax

```php
public function GenerateCsrfToken(): \stdClass
```

---

### VerifyCsrfToken

#### Syntax

```php
public function VerifyCsrfToken(\stdClass $csrfToken): bool
```

#### Parameters

- **$csrfToken**

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
