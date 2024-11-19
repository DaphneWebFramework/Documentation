# CPath

CPath is a class for manipulating file system paths.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(string|\Stringable $value = '')
```

#### Parameters

- **$value**: (Optional) The path value to store. If omitted, defaults to an empty string. If a `CPath` or `CString` instance is provided, its value is cloned. If a native string is provided, it is directly used. For other `Stringable` instances, their string representations are used.

---

### __toString

Returns the string representation for use in string contexts.

#### Syntax

```php
public function __toString(): string
```

#### Return Value

The path value stored in the instance.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
