# CUrl

CUrl is a class for manipulating URLs.

## Methods

### Join

Joins multiple URL segments into a single URL.

#### Syntax

```php
public static function Join(string|\Stringable ...$segments): static
```

#### Parameters

- **$segments**: A list of URL segments to join.

#### Return Value

A new instance representing the joined URL.

#### See Also

- [`Extend`](#Extend)

---

### Extend

Appends one or more segments to the current URL.

#### Syntax

```php
public function Extend(string|\Stringable ...$segments): static
```

#### Parameters

- **$segments**: One or more URL segments to append.

#### Return Value

A new instance with the segments appended.

#### See Also

- [`Join`](#Join)

---

### EnsureLeadingSlash

Ensures the URL starts with a slash.

If the URL does not already start with a slash, one is inserted at the
beginning.

#### Syntax

```php
public function EnsureLeadingSlash(): self
```

#### Return Value

The current instance if the instance already starts with a slash.

---

### EnsureTrailingSlash

Ensures the URL ends with a slash.

If the URL does not already end with a slash, one is appended at the
end.

#### Syntax

```php
public function EnsureTrailingSlash(): self
```

#### Return Value

The current instance if the instance already ends with a slash.

---

### TrimLeadingSlashes

Removes slashes from the start of the URL.

#### Syntax

```php
public function TrimLeadingSlashes(): self
```

#### Return Value

The current instance if the instance has no leading slashes.

---

### TrimTrailingSlashes

Removes slashes from the end of the URL.

#### Syntax

```php
public function TrimTrailingSlashes(): self
```

#### Return Value

The current instance if the instance has no trailing slashes.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
