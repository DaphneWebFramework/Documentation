# CPath

CPath is a class for manipulating file system paths.

## Methods

### __construct

Constructs a new instance.

Leading and trailing whitespace are trimmed when storing the specified
path value.

#### Syntax

```php
public function __construct(string|\Stringable $value = '')
```

#### Parameters

- **$value**: (Optional) The path value to store. If omitted, defaults to an empty string. If given a `CPath` instance, its value is copied. For a `Stringable` instance, its string representation is used, and for a native string, the value is used directly.

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

If the path does not already start with a slash, one is inserted at the
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

Ensures the path ends with a trailing slash.

If the path does not already end with a slash, one is appended at the
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

Leading slashes include both forward slashes and backslashes depending on
the operating system.

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

Trailing slashes include both forward slashes and backslashes depending
on the operating system.

This method directly modifies the current instance.

#### Syntax

```php
public function TrimTrailingSlashes(): self
```

#### Return Value

The current instance.

---

### IsFile

Determines whether the path points to an existing file.

#### Syntax

```php
public function IsFile(): bool
```

#### Return Value

Returns `true` if the path points to a file; otherwise, `false`.

---

### IsDirectory

Determines whether the path points to an existing directory.

#### Syntax

```php
public function IsDirectory(): bool
```

#### Return Value

Returns `true` if the path points to a directory; otherwise, `false`.

---

### ToAbsolute

Returns the canonical absolute form of the path.

Resolves the path to its absolute and canonical form by expanding all
symbolic links, resolving `/./`, `/../`, and extra `/` characters.
On success, trailing slashes are also removed.

The method fails if the path does not exist or if the script lacks
sufficient permissions to access directories in the hierarchy.

If the path is empty, it is interpreted as the current directory.

#### Syntax

```php
public function ToAbsolute(): ?\Harmonia\Core\CPath
```

#### Return Value

A new `CPath` instance containing the canonical absolute path if successful, or `null` if the method fails.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
