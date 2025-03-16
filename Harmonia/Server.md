# Server

Provides structured access to server environment data.

## Methods

### IsSecure

Checks if the connection is secure.

#### Syntax

```php
public function IsSecure(): bool
```

#### Return Value

Returns `true` if the connection is secure (e.g., HTTPS); otherwise, `false`.

---

### Url

Retrieves the web server's root URL, including the protocol and hostname.

#### Syntax

```php
public function Url(): ?\Harmonia\Core\CUrl
```

#### Return Value

A `CUrl` instance representing the root URL (e.g., "http://localhost" or "https://example.com"), or `null` if the server name is not set.

---

### Path

Retrieves the web server's root directory path.

#### Syntax

```php
public function Path(): ?\Harmonia\Core\CPath
```

#### Return Value

A `CPath` instance representing the root directory path (e.g., "C:/xampp/htdocs" or "/var/www/html"), or `null` if the document root is not set.

---

### RequestMethod

Retrieves the request method.

#### Syntax

```php
public function RequestMethod(): ?\Harmonia\Core\CString
```

#### Return Value

A `CString` instance representing the request method (e.g., "GET", "POST", "PUT", "DELETE"), or `null` if the request method is not set.

---

### RequestUri

Retrieves the request URI.

The request URI is the part of the URL that comes after the domain name,
including the query string and fragment identifier.

#### Syntax

```php
public function RequestUri(): ?\Harmonia\Core\CString
```

#### Return Value

A `CString` instance representing the request URI (e.g., "/index.php", "/index.php?foo=bar#section"), or `null` if the request URI is not set.

---

### RequestHeaders

Retrieves the HTTP headers from the request.

This method extracts headers from `$_SERVER`, including those prefixed
with 'HTTP_' and standard headers such as 'CONTENT_TYPE' and 'CONTENT_LENGTH'.

All header names are converted to lowercase, with underscores (`_`)
replaced by hyphens (`-`). Header values remain unchanged.

#### Syntax

```php
public function RequestHeaders(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` instance where the keys are formatted header names and the values are their respective header values.

---

### ClientAddress

Retrieves the client's IP address.

#### Syntax

```php
public function ClientAddress(): string
```

#### Return Value

The client's IP address.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
