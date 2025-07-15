# Request

Represents an HTTP request.

## Methods

### Method_

Retrieves the HTTP request method.

PHPUnit 12 introduced a restriction preventing the use of "Method" as a
method name. To comply with this, "Method_" was chosen instead.

#### Syntax

```php
public function Method_(): ?\Harmonia\Http\RequestMethod
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

If `apache_request_headers()` is available, it is used to fetch the
headers. Otherwise, headers are retrieved from the `$_SERVER` superglobal.

All header names are converted to lowercase to ensure predictable
case-sensitive lookups.

#### Syntax

```php
public function Headers(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` instance where the keys are lowercase header names and the values are their respective header values.

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
public function Body(): ?string
```

#### Return Value

The raw body content, or `null` if an error occurs.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
