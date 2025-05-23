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

### IsLink

Determines whether the path points to an existing symbolic link.

#### Syntax

```php
public function IsLink(): bool
```

#### Return Value

Returns `true` if the path points to a symbolic link; otherwise, `false`.

#### See Also

- [`ReadLink`](#ReadLink)

---

### ReadLink

Reads the target path of a symbolic link.

#### Syntax

```php
public function ReadLink(): ?\Harmonia\Core\CPath
```

#### Return Value

A new `CPath` instance containing the target of the symbolic link if successful, or `null` if the method fails.

#### See Also

- [`IsLink`](#IsLink)

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
