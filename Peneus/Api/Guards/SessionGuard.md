# SessionGuard

A guard that verifies whether the request is from a logged-in user,
optionally enforcing a minimum role requirement.

## Methods

### __construct

Constructs a new instance with an optional minimum role.

#### Syntax

```php
public function __construct(?\Peneus\Model\Role $minimumRole = null)
```

#### Parameters

- **$minimumRole**: (Optional) The minimum role required for the request. If not provided, the guard will only check if the user is logged in without enforcing a specific role. If a role is provided, the guard will ensure that the logged-in user's role meets or exceeds this minimum requirement.

---

### Verify

Verifies that the request is from a logged-in user.

If a minimum role is set, also ensures the user has at least that role.

#### Syntax

```php
public function Verify(): bool
```

#### Return Value

Returns `true` if the user is logged in and satisfies the role requirement, if any. Otherwise, returns `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
