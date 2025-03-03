# Response

Represents an HTTP response.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct()
```

---

### SetStatusCode

Sets the HTTP status code.

#### Syntax

```php
public function SetStatusCode(\Harmonia\Http\StatusCode $statusCode): self
```

#### Parameters

- **$statusCode**: The HTTP status code.

#### Return Value

The current instance.

---

### SetHeader

Adds or updates an HTTP header.

#### Syntax

```php
public function SetHeader(string $name, string $value): self
```

#### Parameters

- **$name**: The header name.
- **$value**: The header value.

#### Return Value

The current instance.

---

### SetCookie

Adds or updates a cookie.

#### Syntax

```php
public function SetCookie(string $name, string $value): self
```

#### Parameters

- **$name**: The cookie name.
- **$value**: The cookie value. If empty, the cookie is deleted.

#### Return Value

The current instance.

---

### DeleteCookie

Deletes a cookie.

This is a convenience method that calls `SetCookie` with an empty value.

#### Syntax

```php
public function DeleteCookie(string $name): self
```

#### Parameters

- **$name**: The cookie name.

#### Return Value

The current instance.

---

### SetBody

Sets the response body.

#### Syntax

```php
public function SetBody(string|\Stringable $body): self
```

#### Parameters

- **$body**: The response body.

#### Return Value

The current instance.

---

### Send

Sends the response.

#### Syntax

```php
public function Send(): void
```

---

### Redirect

Redirects the client to a new URL.

#### Syntax

```php
public function Redirect(string $url, bool $exitScript = true): void
```

#### Parameters

- **$url**: The URL to redirect to.
- **$exitScript**: (Optional) If `true`, the script will exit after sending the response. Default is `true`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
