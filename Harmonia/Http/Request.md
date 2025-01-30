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

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
