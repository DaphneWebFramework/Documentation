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

### Join

Joins multiple path segments into a single path.

#### Syntax

```php
public static function Join(string ...$segments): \Harmonia\Core\CPath
```

#### Parameters

- **$segments**: A list of path segments to join.

#### Return Value

A new `CPath` instance representing the joined path.

---

### EnsureLeadingSlash

Ensures the path starts with a leading slash.

If the path does not already start with a valid slash (forward slash or
backslash, depending on the operating system), a directory separator is
inserted at the start of the path.

#### Syntax

```php
public function EnsureLeadingSlash(): \Harmonia\Core\CPath
```

#### Return Value

The current instance.

---

### EnsureTrailingSlash

Ensures the path ends with a trailing slash.

If the path does not already end with a valid slash (forward slash or
backslash, depending on the operating system), a directory separator is
appended to the end of the path.

#### Syntax

```php
public function EnsureTrailingSlash(): \Harmonia\Core\CPath
```

#### Return Value

The current instance.

---

### TrimLeadingSlashes

Removes all leading slashes.

Leading slashes include both forward slashes and backslashes depending on
the operating system.

#### Syntax

```php
public function TrimLeadingSlashes(): \Harmonia\Core\CPath
```

#### Return Value

The current instance.

---

### TrimTrailingSlashes

Removes all trailing slashes.

Trailing slashes include both forward slashes and backslashes depending
on the operating system.

#### Syntax

```php
public function TrimTrailingSlashes(): \Harmonia\Core\CPath
```

#### Return Value

The current instance.

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
