# CString

CString is a wrapper class for string manipulation, allowing the use of both
single-byte and multibyte encodings.

This class requires PHP's `mbstring` extension for multibyte encoding support.

## Methods

### __construct

Constructs a new instance of CString.

#### Syntax

```php
public function __construct(string|\Stringable $value = '', ?string $encoding = null)
```

#### Parameters

- **$value**: The string value to store. If a `CString` instance is provided, the value, encoding, and single-byte/multibyte status are copied from the original instance.
- **$encoding**: The encoding to use (e.g., 'UTF-8', 'ISO-8859-1'). If `null`, defaults to the return value of `mb_internal_encoding`. This parameter is ignored when the `$value` is an instance of `CString`.

---

### __toString

Converts the CString instance to a string.

#### Syntax

```php
public function __toString(): string
```

#### Return Value

The string value stored in the instance.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
