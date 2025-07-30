# CPath

CPath is a class for manipulating file system paths.

## Methods

### Join

Joins multiple path segments into a single path.

#### Syntax

```php
public static function Join(string|\Stringable ...$segments): \Harmonia\Core\CPath
```

#### Parameters

- **$segments**: A list of path segments to join.

#### Return Value

A new `CPath` instance representing the joined path.

---

### EnsureLeadingSlash

Ensures the path starts with a slash.

If the path does not already start with a slash, one is inserted at the
beginning.

#### Syntax

```php
public function EnsureLeadingSlash(): static
```

#### Return Value

A new instance that starts with a slash.

---

### EnsureTrailingSlash

Ensures the path ends with a slash.

If the path does not already end with a slash, one is appended at the
end.

#### Syntax

```php
public function EnsureTrailingSlash(): static
```

#### Return Value

A new instance that ends with a slash.

---

### TrimLeadingSlashes

Removes slashes from the start of the path.

The slashes include both forward slashes and backslashes depending on
the operating system.

#### Syntax

```php
public function TrimLeadingSlashes(): static
```

#### Return Value

A new instance without slashes at the start.

---

### TrimTrailingSlashes

Removes slashes from the end of the path.

The slashes include both forward slashes and backslashes depending on
the operating system.

#### Syntax

```php
public function TrimTrailingSlashes(): static
```

#### Return Value

A new instance without slashes at the end.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
