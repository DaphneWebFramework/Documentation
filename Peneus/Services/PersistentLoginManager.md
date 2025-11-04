# PersistentLoginManager

Manages the lifecycle of persistent login entries.

## Methods

### __construct

Constructs a new instance by initializing the dependencies.

#### Syntax

```php
public function __construct()
```

---

### Create

Creates a new persistent login entry for an authenticated user.

#### Syntax

```php
public function Create(int $accountId): void
```

#### Parameters

- **$accountId**: The account ID of an authenticated user.

#### Exceptions

- **\RuntimeException**: If an error occurs while storing the persistent login record or setting the associated cookie.

---

### Delete

Deletes the persistent login entry of the currently logged-in user.

#### Syntax

```php
public function Delete(): void
```

#### Exceptions

- **\RuntimeException**: If an error occurs while deleting the persistent login record or the associated cookie.

---

### Resolve

Attempts to resolve the account ID from the persistent login entry.

#### Syntax

```php
public function Resolve(): int|null
```

#### Return Value

The account ID of the resolved account, or `null` if no valid persistent login entry is available.

---

### Rotate

Rotates the persistent login entry of the currently logged-in user.

#### Syntax

```php
public function Rotate(int $accountId): void
```

#### Parameters

- **$accountId**: The account ID of an authenticated user.

#### Exceptions

- **\RuntimeException**: If an error occurs while storing the persistent login record or setting the associated cookie.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
