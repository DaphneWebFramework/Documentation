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
public function Url(): string
```

#### Return Value

The fully qualified URL (e.g., "http://localhost" or "https://example.com").

---

### Path

Retrieves the web server's root directory path.

#### Syntax

```php
public function Path(): string
```

#### Return Value

The root directory path (e.g., "C:/xampp/htdocs" or "/var/www/html").

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
