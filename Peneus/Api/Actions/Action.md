# Action

Base class for API actions with security enforcement.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct()
```

---

### AddGuard

Adds a guard that must pass verification before the action can execute.

#### Syntax

```php
public function AddGuard(\Peneus\Api\Guards\IGuard $guard): self
```

#### Parameters

- **$guard**: The guard to add.

#### Return Value

The current instance.

---

### Execute

Executes the action after verifying all assigned guards.

#### Syntax

```php
public function Execute(): mixed
```

#### Return Value

The result of the executed action.

#### Exceptions

- **\RuntimeException**: If any guard verification fails, or any other runtime error occurs during the execution of the action.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
