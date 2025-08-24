# HeaderTokenGuard

A guard that verifies a CSRF token sent via custom HTTP header against
a hash value stored in a cookie.

This class ensures protection against session hijacking and CSRF attacks by
comparing the header-sent token with its hashed counterpart stored in an
application-specific cookie.

## Methods

### __construct

Constructs a new instance using the CSRF token from HTTP headers and the
application-specific CSRF cookie name.

#### Syntax

```php
public function __construct()
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
