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

Returns `true` if the connection is secure (e.g., HTTPS); otherwise, returns `false`.

---

### HostName

Returns the hostname.

#### Syntax

```php
public function HostName(): string
```

#### Return Value

The server name as defined by the `SERVER_NAME` key in the `$_SERVER` superglobal. Returns an empty string if the key does not exist.

---

### HostUrl

Returns the full server URL, including the protocol and hostname.

#### Syntax

```php
public function HostUrl(): string
```

#### Return Value

The full URL constructed from the protocol (http/https) and the server name.

---

### RootDirectory

Returns the root directory path.

#### Syntax

```php
public function RootDirectory(): string
```

#### Return Value

The directory path as defined by the `DOCUMENT_ROOT` key in the `$_SERVER` superglobal, e.g., "C:/xampp/htdocs". Returns an empty string if the key does not exist.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
