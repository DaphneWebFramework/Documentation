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

A new `CUrl` instance representing the root URL (e.g., "http://localhost" or "https://example.com"), or `null` if the server name is not set.

---

### Path

Retrieves the web server's root directory path.

#### Syntax

```php
public function Path(): ?\Harmonia\Core\CPath
```

#### Return Value

A new `CPath` instance representing the root directory path (e.g., "C:/xampp/htdocs" or "/var/www/html"), or `null` if the document root is not set.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
