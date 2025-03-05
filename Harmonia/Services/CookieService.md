# CookieService

Provides cookie management services.

## Methods

### SetCookie

Adds or updates a cookie.

#### Syntax

```php
public function SetCookie(string $name, string $value): bool
```

#### Parameters

- **$name**: The cookie name.
- **$value**: The cookie value. If empty, the cookie is deleted.

#### Return Value

Returns `true` if the cookie is set successfully. Returns `false` if the HTTP headers have already been sent or if the cookie could not be set for any other reason.

---

### DeleteCookie

Deletes a cookie.

This is a convenience method that calls `SetCookie` with an empty value.

#### Syntax

```php
public function DeleteCookie(string $name): bool
```

#### Parameters

- **$name**: The cookie name.

#### Return Value

Returns `true` if the cookie is deleted successfully. Returns `false` if the HTTP headers have already been sent or if the cookie could not be deleted for any other reason.

#### See Also

- [`SetCookie`](#SetCookie)

---

### AppSpecificCookieName

Generates an application-specific cookie name combined with the given
suffix.

The application name is retrieved from the configuration. If no
application name is set, a default value is used.

#### Syntax

```php
public function AppSpecificCookieName(string $suffix): string
```

#### Parameters

- **$suffix**: The suffix to append to the application name. This value cannot be empty.

#### Return Value

The generated cookie name, always in uppercase and following the `{APPNAME}_{SUFFIX}` format.

#### Exceptions

- **\InvalidArgumentException**: If the suffix is empty.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
