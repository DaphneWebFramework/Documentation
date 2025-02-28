# CookieService

Provides cookie management services.

## Methods

### SetCookie

Adds or updates a cookie.

#### Syntax

```php
public function SetCookie(string $name, string|false $value): bool
```

#### Parameters

- **$name**: The cookie name.
- **$value**: The cookie value. If `false`, the cookie is deleted.

#### Return Value

Returns `true` if the cookie is set successfully, `false` otherwise.

---

### DeleteCookie

Deletes a cookie.

This is a convenience method that calls `SetCookie` with the value set to
`false`.

#### Syntax

```php
public function DeleteCookie(string $name): bool
```

#### Parameters

- **$name**: The cookie name.

#### Return Value

Returns `true` if the cookie is deleted successfully, `false` otherwise.

#### See Also

- [`SetCookie`](#SetCookie)

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
