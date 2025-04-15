# CustomPolicy

A flexible access policy that delegates access control logic to a user-defined callback.

This policy allows project-specific logic to be injected without defining a
standalone class. The provided closure is responsible for enforcing access
by performing any required checks, redirects, or side effects.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(\Closure $callback)
```

#### Parameters

- **$callback**: A closure that performs access enforcement. It should redirect, send an error response, or take other appropriate action when access is denied.

---

### Enforce

Executes the user-defined callback to enforce access.

#### Syntax

```php
public function Enforce(): void
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
