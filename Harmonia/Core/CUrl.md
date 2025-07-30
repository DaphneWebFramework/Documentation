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

Ensures the URL starts with a slash.

If the URL does not already start with a slash, one is inserted at the
beginning.

#### Syntax

```php
public function EnsureLeadingSlash(): static
```

#### Return Value

A new instance that starts with a slash.

---

### EnsureTrailingSlash

Ensures the URL ends with a slash.

If the URL does not already end with a slash, one is appended at the
end.

#### Syntax

```php
public function EnsureTrailingSlash(): static
```

#### Return Value

A new instance that ends with a slash.

---

### TrimLeadingSlashes

Removes slashes from the start of the URL.

#### Syntax

```php
public function TrimLeadingSlashes(): static
```

#### Return Value

A new instance without slashes at the start.

---

### TrimTrailingSlashes

Removes slashes from the end of the URL.

#### Syntax

```php
public function TrimTrailingSlashes(): static
```

#### Return Value

A new instance without slashes at the end.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
