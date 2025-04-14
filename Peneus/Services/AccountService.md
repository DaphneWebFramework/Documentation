# AccountService

Provides account-related utilities.

## Methods

### IntegrityCookieName

Returns the name of the session integrity cookie.

This cookie stores a hashed version of the session integrity token,
ensuring that the session has not been hijacked or tampered with.

The generated name includes the application name to avoid conflicts
when multiple applications share the same framework.

#### Syntax

```php
public function IntegrityCookieName(): string
```

#### Return Value

The session integrity cookie name.

---

### AuthenticatedAccount

Retrieves the currently authenticated account.

This method first verifies session integrity by checking whether the
session integrity token matches its hashed counterpart stored in the
cookie. If validation succeeds, the associated account is retrieved.

If the session is compromised or no account is found, the session
is destroyed to prevent unauthorized access.

#### Syntax

```php
public function AuthenticatedAccount(): ?\Peneus\Model\Account
```

#### Return Value

The authenticated account, or `null` if authentication fails.

#### Exceptions

- **\RuntimeException**: If the session cannot be started, closed, or destroyed.

---

### RoleOfAuthenticatedAccount

Retrieves the role of the authenticated account.

#### Syntax

```php
public function RoleOfAuthenticatedAccount(): ?\Peneus\Model\Role
```

#### Return Value

The role of the authenticated account, or `null` if not set in the session.

#### Exceptions

- **\RuntimeException**: If the session cannot be started or closed.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
