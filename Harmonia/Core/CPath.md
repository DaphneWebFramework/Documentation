# CPath

CPath is a class for manipulating file system paths.

## Methods

### Join

Joins multiple path segments into a single path.

#### Syntax

```php
public static function Join(string|\Stringable ...$segments): static
```

#### Parameters

- **$segments**: A list of path segments to join.

#### Return Value

A new instance representing the joined path.

#### See Also

- [`ExtendInPlace`](#ExtendInPlace)
- [`Extend`](#Extend)

---

### ExtendInPlace

Appends one or more segments to the current path.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function ExtendInPlace(string|\Stringable ...$segments): self
```

#### Parameters

- **$segments**: One or more path segments to append.

#### Return Value

The current instance.

#### See Also

- [`ExtendInPlace`](#ExtendInPlace)
- [`Join`](#Join)

---

### Extend

Appends one or more segments to the current path.

#### Syntax

```php
public function Extend(string|\Stringable ...$segments): static
```

#### Parameters

- **$segments**: One or more path segments to append.

#### Return Value

A new instance with the segments appended.

#### See Also

- [`ExtendInPlace`](#ExtendInPlace)
- [`Join`](#Join)

---

### EnsureLeadingSlash

Ensures the path starts with a slash.

If the path does not already start with a slash, one is inserted at the
beginning.

#### Syntax

```php
public function EnsureLeadingSlash(): self
```

#### Return Value

The current instance if the instance already starts with a slash.

---

### EnsureTrailingSlash

Ensures the path ends with a slash.

If the path does not already end with a slash, one is appended at the
end.

#### Syntax

```php
public function EnsureTrailingSlash(): self
```

#### Return Value

The current instance if the instance already ends with a slash.

---

### TrimLeadingSlashes

Removes slashes from the start of the path.

The slashes include both forward slashes and backslashes depending on
the operating system.

#### Syntax

```php
public function TrimLeadingSlashes(): self
```

#### Return Value

The current instance if the instance has no leading slashes.

---

### TrimTrailingSlashes

Removes slashes from the end of the path.

The slashes include both forward slashes and backslashes depending on
the operating system.

#### Syntax

```php
public function TrimTrailingSlashes(): self
```

#### Return Value

The current instance if the instance has no trailing slashes.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
