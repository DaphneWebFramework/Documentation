# MembersPolicy

Restricts access to logged-in users, optionally requiring a minimum role.

## Methods

### __construct

Constructs a new instance with an optional minimum role.

#### Syntax

```php
public function __construct(\Peneus\Model\Role $minimumRole = Role::None)
```

#### Parameters

- **$minimumRole**: (Optional) The minimum role required to access the page. Defaults to `Role::None`.

---

### Enforce

Restricts access to logged-in users.

If no user is signed in, the user is redirected to the login page. If a
minimum role is specified, the logged-in user's account role is checked
against it. If the user's role is insufficient, an HTTP 401 Unauthorized
response is sent and execution is terminated.

#### Syntax

```php
public function Enforce(): void
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
