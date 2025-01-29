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
public function RequestMethod(): ?string
```

#### Return Value

The request method (e.g., "GET", "POST", "PUT", "DELETE"), or `null` if the request method is not set.

---

### RequestUri

Retrieves the request URI.

#### Syntax

```php
public function RequestUri(): ?string
```

#### Return Value

The request URI including the query string and fragment if any (e.g., "/index.php?foo=bar#section"), or `null` if the request URI is not set.

---

### RequestHeaders

Retrieves the HTTP headers from the request.

This method iterates through the `$_SERVER` superglobal and extracts
headers that start with 'HTTP_'. It then formats the header names by
removing the 'HTTP_' prefix, converting underscores to hyphens, and
capitalizing the first letter of each word while lowercasing the rest.

Some headers, such as 'CONTENT_TYPE' and 'CONTENT_LENGTH', do not start
with 'HTTP_' but are still included in the result.

Example transformation:
- "HTTP_USER_AGENT" → "User-Agent"
- "X_CUSTOM_HEADER" → "X-Custom-Header"
- "CONTENT_TYPE" → "Content-Type"
- "CONTENT_LENGTH" → "Content-Length"

#### Syntax

```php
public function RequestHeaders(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` instance where the keys are formatted header names and the values are their respective header values.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
