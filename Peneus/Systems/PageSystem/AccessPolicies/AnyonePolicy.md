# AnyonePolicy

Allows access to anyone, including both authenticated and anonymous users.

This is the default policy when no explicit access policy is assigned to a
page.

## Methods

### Enforce

Allows access unconditionally.

This method performs no checks and permits all users to access the page,
including both anonymous and authenticated users.

#### Syntax

```php
public function Enforce(): void
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
