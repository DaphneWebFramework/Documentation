# CUrl

CUrl is a class for manipulating URLs.

## Methods

### Join

Joins multiple URL segments into a single URL.

#### Syntax

```php
public static function Join(string|\Stringable ...$segments): \Harmonia\Core\CUrl
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
