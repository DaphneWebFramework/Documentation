# AccountService

Provides account-related utilities.

## Methods

### CreateSession

Creates a new session for an authenticated user.

#### Syntax

```php
public function CreateSession(int $accountId): void
```

#### Parameters

- **$accountId**: The account ID of an authenticated user.

#### Exceptions

- **\RuntimeException**: If an error occurs while establishing the session or setting the associated cookie.

---

### DeleteSession

Deletes the session of the currently logged-in user.

#### Syntax

```php
public function DeleteSession(): void
```

#### Exceptions

- **\RuntimeException**: If an error occurs while deleting the session or the associated cookie.

---

### CreatePersistentLogin

Creates a new persistent login entry for an authenticated user.

#### Syntax

```php
public function CreatePersistentLogin(int $accountId): void
```

#### Parameters

- **$accountId**: The account ID of an authenticated user.

#### Exceptions

- **\RuntimeException**: If an error occurs while storing the persistent login record or setting the associated cookie.

---

### DeletePersistentLogin

Deletes the persistent login entry of the currently logged-in user.

#### Syntax

```php
public function DeletePersistentLogin(): void
```

#### Exceptions

- **\RuntimeException**: If an error occurs while deleting the persistent login record or the associated cookie.

---

### LoggedInAccount

Retrieves the account of the currently logged-in user.

This method first tries to resolve the account from the session. If not
found, it attempts to log in the user using the persistent login feature.

#### Syntax

```php
public function LoggedInAccount(): ?\Peneus\Model\AccountView
```

#### Return Value

The account of the currently logged-in user, or `null` if no valid session or persistent login entry is available.

---

### RegisterDeletionHook

Registers a hook to be triggered during account deletion.

#### Syntax

```php
public function RegisterDeletionHook(\Peneus\Api\Hooks\IAccountDeletionHook $hook): void
```

#### Parameters

- **$hook**: The hook implementation to be registered.

---

### DeletionHooks

Returns all registered account deletion hooks.

#### Syntax

```php
public function DeletionHooks(): \Peneus\Api\Hooks\IAccountDeletionHook[]
```

#### Return Value

An array of registered deletion hook instances.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
