# CookieService

Provides cookie management services.

## Methods

### SetCookie

Adds or updates a cookie.

#### Syntax

```php
public function SetCookie(string $name, string $value, ?int $expires = null): void
```

#### Parameters

- **$name**: The cookie name.
- **$value**: The cookie value. If empty, the cookie is deleted.
- **$expires**: (Optional) The cookie's expiration time, in seconds since the Unix epoch. If not specified, the cookie will expire at the end of the browser session.

#### Exceptions

- **\RuntimeException**: If the HTTP headers have already been sent or if the cookie could not be set for any other reason.

---

### DeleteCookie

Deletes a cookie.

This is a convenience method that calls `SetCookie` with an empty value.

#### Syntax

```php
public function DeleteCookie(string $name): void
```

#### Parameters

- **$name**: The cookie name.

#### Exceptions

- **\RuntimeException**: If the HTTP headers have already been sent or if the cookie could not be deleted for any other reason.

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

### SetCsrfCookie

Adds or updates the CSRF cookie.

#### Syntax

```php
public function SetCsrfCookie(string $value): void
```

#### Parameters

- **$value**: The CSRF cookie value. If empty, the cookie is deleted.

#### Exceptions

- **\RuntimeException**: If the HTTP headers have already been sent or if the cookie could not be set for any other reason.

---

### DeleteCsrfCookie

Deletes the CSRF cookie.

#### Syntax

```php
public function DeleteCsrfCookie(): void
```

#### Exceptions

- **\RuntimeException**: If the HTTP headers have already been sent or if the cookie could not be deleted for any other reason.

---

### CsrfCookieName

Retrieves the CSRF cookie name.

#### Syntax

```php
public function CsrfCookieName(): string
```

#### Return Value

The CSRF cookie name.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
