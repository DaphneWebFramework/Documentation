# TokenGuard

A guard that verifies a token against a hash value stored in a cookie.

This class ensures protection against session hijacking and CSRF attacks by
comparing the provided token with its hashed counterpart stored in a cookie.

## Methods

### __construct

Constructs a new instance with the specified token and cookie name.

#### Syntax

```php
public function __construct(string $token, string $cookieName)
```

#### Parameters

- **$token**: The token value to verify.
- **$cookieName**: The name of the cookie storing the expected token hash.

---

### Verify

Verifies whether the provided token matches its hashed version stored
in the specified cookie.

#### Syntax

```php
public function Verify(): bool
```

#### Return Value

Returns `true` if the cookie exists and its value matches the expected token, otherwise `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
