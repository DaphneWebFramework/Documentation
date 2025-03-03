# CsrfToken

Represents a CSRF token and its hashed counterpart stored in a cookie.

## Methods

### __construct

Creates a new instance.

#### Syntax

```php
public function __construct(string $token, string $cookieValue)
```

#### Parameters

- **$token**: The token value.
- **$cookieValue**: The token hash stored in a cookie.

---

### Token

Gets the token value.

#### Syntax

```php
public function Token(): string
```

#### Return Value

The token value.

---

### CookieValue

Gets the token hash stored in a cookie.

#### Syntax

```php
public function CookieValue(): string
```

#### Return Value

The token hash.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
