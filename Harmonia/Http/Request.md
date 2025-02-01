# Request

Represents an HTTP request.

## Methods

### Method

Retrieves the HTTP request method.

#### Syntax

```php
public function Method(): ?\Harmonia\Http\RequestMethod
```

#### Return Value

The request method, or `null` if the request method is not available or unsupported.

---

### Path

Retrieves the path component of the request URI.

This method extracts the path from the request URI, removing any query
strings (`?query=value`) or fragments (`#fragment`). The trailing slash
is also trimmed for consistency.

#### Syntax

```php
public function Path(): ?\Harmonia\Core\CString
```

#### Return Value

The request path, or `null` if the request path is not available.

---

### QueryParams

Retrieves the query parameters from the `$_GET` superglobal.

#### Syntax

```php
public function QueryParams(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` instance containing the query parameters.

---

### FormParams

Retrieves the form parameters from the `$_POST` superglobal.

The form parameters are populated when the request method is `POST` and
the `Content-Type` header is either `application/x-www-form-urlencoded`
or `multipart/form-data`.

#### Syntax

```php
public function FormParams(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` instance containing the form parameters.

---

### Files

Retrieves the uploaded files from the `$_FILES` superglobal.

#### Syntax

```php
public function Files(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` instance containing the uploaded files.

---

### Cookies

Retrieves the cookies from the `$_COOKIE` superglobal.

#### Syntax

```php
public function Cookies(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` instance containing the cookies.

---

### Headers

Retrieves the HTTP headers.

This method obtains headers using `apache_request_headers()` if available.
Otherwise, it emulates the behavior by extracting headers from `$_SERVER`,
specifically those prefixed with 'HTTP_'.

#### Syntax

```php
public function Headers(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` instance containing the HTTP headers with keys formatted in title case with hyphens (e.g., "User-Agent", "Content-Type").

---

### Body

Retrieves the raw request body content.

This method reads and returns the raw body content (payload) directly
from the `php://input` stream. It provides the unprocessed request data,
which can include various formats like JSON, XML, or binary content.

Be aware that `php://input` is not available in POST requests with a
`Content-Type` of `multipart/form-data`, as PHP processes these requests
differently. If raw input is required for file uploads, consider using
the PUT method instead.

#### Syntax

```php
public function Body(): ?\Harmonia\Core\CString
```

#### Return Value

A `CString` instance containing the raw body data, or `null` if an error occurs.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
