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

### GetAuthenticatedAccount

Retrieves the currently authenticated account.

This method first verifies session integrity by checking whether the
session integrity token matches its hashed counterpart stored in the
cookie. If validation succeeds, the associated account is retrieved.

If the session is compromised or no account is found, the session
is destroyed to prevent unauthorized access.

#### Syntax

```php
public function GetAuthenticatedAccount(): ?\Peneus\Model\Account
```

#### Return Value

The authenticated account, or `null` if authentication fails.

#### Exceptions

- **\RuntimeException**: If the session cannot be started or destroyed.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
