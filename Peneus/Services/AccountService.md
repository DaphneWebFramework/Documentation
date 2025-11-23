# AccountService

Provides account-related utilities.

## Methods

### CreateSession

Creates a new session for an authenticated user.

#### Syntax

```php
public function CreateSession(int $accountId, bool $persistent = \Peneus\Services\false): void
```

#### Parameters

- **$accountId**: The account ID of an authenticated user.
- **$persistent**: (Optional) If `true`, a persistent login record will also be created and the associated cookie set. Defaults to `false`.

#### Exceptions

- **\RuntimeException**: If an error occurs while establishing the session, setting the session-binding cookie, storing the persistent login record, or setting the persistent login cookie.

---

### DeleteSession

Deletes the session of the currently logged-in user.

#### Syntax

```php
public function DeleteSession(): void
```

#### Exceptions

- **\RuntimeException**: If an error occurs while deleting the session, removing the session-binding cookie, deleting the persistent login record, or removing the persistent login cookie.

---

### SessionAccount

Retrieves the account of the currently logged-in user.

This method first tries to resolve the account from the session. If not
found, it attempts to log in the user using the persistent login feature.

The result of this method is cached for the lifetime of the request,
avoiding unnecessary database queries; subsequent calls return the same
cached result (including `null`) until the cache is reset when session
state changes (e.g. login or logout).

#### Syntax

```php
public function SessionAccount(): ?\Peneus\Model\AccountView
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
