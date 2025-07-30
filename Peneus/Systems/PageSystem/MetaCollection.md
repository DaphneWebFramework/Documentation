# MetaCollection

Stores and manages page-level meta tags.

## Methods

### __construct

Constructs a new instance and applies default tags from configuration.

#### Syntax

```php
public function __construct()
```

---

### Has

Determines whether a meta tag with the given name and type exists.

#### Syntax

```php
public function Has(string $name, string $type): bool
```

#### Parameters

- **$name**: The name of the meta tag (e.g., `description`, `og:title`).
- **$type**: The meta tag type (e.g., `name`, `property`, `itemprop`).

#### Return Value

Returns `true` if the meta tag exists, `false` otherwise.

---

### Set

Adds or replaces a meta tag.

#### Syntax

```php
public function Set(string $name, string|\Stringable $content, string $type = 'name'): void
```

#### Parameters

- **$name**: The name of the meta tag (e.g., `description`, `og:title`).
- **$content**: The content of the meta tag.
- **$type**: (Optional) The attribute type (e.g., `name`, `property`, `itemprop`). Defaults to `name`.

---

### Remove

Removes a specific meta tag.

If the tag does not exist, the method does nothing.

#### Syntax

```php
public function Remove(string $name, string $type): void
```

#### Parameters

- **$name**: The name of the tag to remove.
- **$type**: The attribute type (e.g., `name`, `property`, `itemprop`).

---

### RemoveAll

Removes all stored meta tags.

#### Syntax

```php
public function RemoveAll(): void
```

---

### Items

Returns all stored meta tags grouped by attribute type.

#### Syntax

```php
public function Items(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` of meta tag groups. Each key is the type (e.g., `name`, `property`, `itemprop`) and each value is a `CArray` of tag names mapped to their contents.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
