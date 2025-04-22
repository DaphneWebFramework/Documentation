# AuthManager

Provides access to the currently logged-in account and associated role,
along with role-based access control.

## Methods

### __construct

Constructs a new instance with uncached account state.

#### Syntax

```php
public function __construct()
```

---

### LoggedInAccount

Returns the currently logged-in user's account.

The result is cached after the first retrieval.

#### Syntax

```php
public function LoggedInAccount(): ?\Peneus\Model\Account
```

#### Return Value

An `Account` object associated with the logged-in user, or `null` if no user is logged in.

---

### LoggedInAccountRole

Returns the role associated with the currently logged-in user's account.

The result is cached after the first retrieval.

#### Syntax

```php
public function LoggedInAccountRole(): \Peneus\Model\Role
```

#### Return Value

The role of the current user, or `Role::None` if no user is logged in or a role is not explicitly assigned to the account.

---

### RequireLogin

Restricts access to logged-in users.

If no user is logged in, the user is redirected to the login page. If a
minimum role is specified, the logged-in user's role is checked against
it. If the user's role is insufficient, the user is redirected to the
error page with an HTTP 401 Unauthorized response.

#### Syntax

```php
public function RequireLogin(\Peneus\Model\Role $minimumRole = Role::None): void
```

#### Parameters

- **$minimumRole**: (Optional) The minimum role required to access the page. Defaults to `Role::None`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
