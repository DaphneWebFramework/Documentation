# FormTokenGuard

A guard that verifies a form-submitted CSRF token against a hash value stored
in a cookie.

This class ensures protection against session hijacking and CSRF attacks by
comparing the form-submitted token with its hashed counterpart stored in an
application-specific cookie.

## Methods

### __construct

Constructs a new instance using the form-submitted CSRF token and the
application-specific CSRF cookie name.

#### Syntax

```php
public function __construct()
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
