# LibraryManager

Manages the frontend libraries to be included in a web page.

This class tracks which libraries are active (either marked as default in
the manifest or added manually by the page). It can add, remove, clear,
and determine which libraries are included in the final list.

## Methods

### __construct

Constructs a new instance by loading the manifest and including all
libraries marked as default in the manifest.

#### Syntax

```php
public function __construct(?\Peneus\Systems\PageSystem\LibraryManifest $manifest = null)
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

#### Syntax

```php
public function Remove(string $name): void
```

#### Parameters

- **$name**: The name of the library to remove.

---

### Clear

Clears all libraries from the set of included libraries.

#### Syntax

```php
public function Clear(): void
```

---

### Included

Returns the list of libraries currently included in the page.

This list includes all libraries that are either marked as default in the
manifest or explicitly added using `Add`, and not removed using `Remove`.
The libraries are returned in the order they appear in the manifest file.

#### Syntax

```php
public function Included(): \Harmonia\Core\CSequentialArray
```

#### Return Value

A list of `LibraryItem` instances that should be rendered in the page, in the same order as declared in the manifest.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
