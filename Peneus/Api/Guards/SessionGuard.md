# SessionGuard

A guard that verifies whether the request is from a logged-in user,
optionally enforcing a minimum role requirement.

## Methods

### __construct

Constructs a new instance with an optional minimum role.

#### Syntax

```php
public function __construct(\Peneus\Model\Role $minimumRole = \Peneus\Model\Role::None)
```

#### Parameters

- **$minimumRole**: (Optional) The minimum role required for the request. Defaults to `Role::None`. When `Role::None` is specified, only login status is enforced.

---

### Verify

Verifies that the request is from a logged-in user and optionally
enforces a minimum role requirement.

#### Syntax

```php
public function Verify(): bool
```

#### Return Value

Returns `true` if the user is logged in and satisfies the role requirement, if any. Otherwise, returns `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
