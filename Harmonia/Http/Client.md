# Client

Performs HTTP requests.

## Methods

### __construct

Constructs a new instance.

By default the request method is initialized to "GET".

#### Syntax

```php
public function __construct()
```

#### Exceptions

- **\RuntimeException**: If the transport layer fails to initialize.

---

### __destruct

Releases the underlying transport resources.

#### Syntax

```php
public function __destruct()
```

---

### Clear

Clears only the request fields back to defaults.

#### Syntax

```php
public function Clear(): self
```

#### Return Value

The current instance.

---

### Method_

Sets the request method.

PHPUnit 12 introduced a restriction preventing the use of "Method" as a
method name. To comply with this, "Method_" was chosen instead.

#### Syntax

```php
public function Method_(string $method): self
```

#### Parameters

- **$method**: The method to set.

#### Return Value

The current instance.

---

### Url

Sets the request URL.

#### Syntax

```php
public function Url(string $url): self
```

#### Parameters

- **$url**: The URL to set.

#### Return Value

The current instance.

---

### Headers

Sets the request headers or returns the response headers.

#### Syntax

```php
public function Headers(array<string,string>|null $headers = null): self|array<string,string>
```

#### Parameters

- **$headers**: Associative array of header name/value pairs to set, or `null` to get the response headers.

#### Return Value

The current instance when setting, or an associative array of response headers when getting. Response headers are returned in lowercase keys.

---

### Body

Sets the request body or returns the response body.

When passing a non‑empty string, the default `Content-Type` header will
be `application/x-www-form-urlencoded` unless you explicitly set your own
(e.g., `application/json`, `application/xml`). Passing an empty string
results in no payload being sent.

When passing an array, it will always be encoded as `multipart/form-data`
with an automatically generated boundary. To send URL‑encoded form data,
you must encode the array yourself (e.g., with `http_build_query()`) and
pass the resulting string instead.

#### Syntax

```php
public function Body(string|array|null $body = null): self|string
```

#### Parameters

- **$body**: The body to set, or `null` to get the response body.

#### Return Value

The current instance when setting, or the response body when getting.

---

### StatusCode

Returns the response status code.

#### Syntax

```php
public function StatusCode(): int
```

#### Return Value

The response status code.

---

### Send

Executes the request and populates the response.

#### Syntax

```php
public function Send(): bool
```

#### Return Value

Returns `true` on success, or `false` if a transport error occurred.

---

### LastError

Returns the details of the last transport error.

#### Syntax

```php
public function LastError(): \stdClass
```

#### Return Value

Object with `code` (int) and `message` (string).

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
