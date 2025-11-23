# LibraryManager

Manages inclusion and exclusion of frontend libraries.

This class maintains a set of library names to be included in a web page and
ensures they are returned in the order defined by the manifest. Libraries may
be added or removed dynamically. Libraries marked as default in the manifest
are included automatically upon instantiation.

## Methods

### __construct

Constructs a new instance by loading the manifest and including all
libraries marked as default in the manifest.

#### Syntax

```php
public function __construct(?\Peneus\Systems\PageSystem\LibraryManifest $manifest = \Peneus\Systems\PageSystem\null)
```

#### Parameters

- **$manifest**: (Optional) The manifest to use. If not specified, a default instance is created.

---

### Add

Adds a library to be included in the page.

#### Syntax

```php
public function Add(string $name): void
```

#### Parameters

- **$name**: The name of the library to add.

#### Exceptions

- **\InvalidArgumentException**: If the library name does not exist in the manifest.

---

### Remove

Removes a library from the set of included libraries.

This method can be used to exclude libraries that were automatically
included by default, or to undo a manual addition. If the library is
not currently included, the method does nothing.

#### Syntax

```php
public function Remove(string $name): void
```

#### Parameters

- **$name**: The name of the library to remove.

---

### RemoveAll

Removes all included libraries.

This method can be used to exclude all libraries that were automatically
included by default, as well as any that were added manually.

#### Syntax

```php
public function RemoveAll(): void
```

---

### Included

Returns the list of libraries to be included in the page.

This list consists of all libraries that were marked as default in the
manifest or explicitly added using `Add`, and not removed using `Remove`.
The libraries are returned in the order they appear in the manifest.

#### Syntax

```php
public function Included(): \Harmonia\Core\CSequentialArray
```

#### Return Value

A list of `LibraryItem` instances.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
