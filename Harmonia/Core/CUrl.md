# CUrl

CUrl is a class for manipulating URLs.

## Methods

### __construct

Constructs a new instance.

Leading and trailing whitespace are trimmed when storing the specified
URL value.

#### Syntax

```php
public function __construct(string|\Stringable $value = '')
```

#### Parameters

- **$value**: (Optional) The URL value to store. If omitted, defaults to an empty string. If given a `CUrl` instance, its value is copied. For a `Stringable` instance, its string representation is used, and for a native string, the value is used directly.

---

### Join

Joins multiple URL segments into a single URL.

#### Syntax

```php
public static function Join(string ...$segments): \Harmonia\Core\CUrl
```

#### Parameters

- **$segments**: A list of URL segments to join.

#### Return Value

A new `CUrl` instance representing the joined URL.

---

### EnsureLeadingSlash

Ensures the URL starts with a leading slash.

If the URL does not already start with a slash, one is inserted at the
beginning.

This method directly modifies the current instance.

#### Syntax

```php
public function EnsureLeadingSlash(): self
```

#### Return Value

The current instance.

---

### EnsureTrailingSlash

Ensures the URL ends with a trailing slash.

If the URL does not already end with a slash, one is appended at the
end.

This method directly modifies the current instance.

#### Syntax

```php
public function EnsureTrailingSlash(): self
```

#### Return Value

The current instance.

---

### TrimLeadingSlashes

Removes all leading slashes.

This method directly modifies the current instance.

#### Syntax

```php
public function TrimLeadingSlashes(): self
```

#### Return Value

The current instance.

---

### TrimTrailingSlashes

Removes all trailing slashes.

This method directly modifies the current instance.

#### Syntax

```php
public function TrimTrailingSlashes(): self
```

#### Return Value

The current instance.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
