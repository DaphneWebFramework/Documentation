# LibraryItem

Represents the metadata for a frontend library declared in `manifest.json`.

This class holds normalized data for a single frontend library (e.g.,
Bootstrap, jQuery), including its associated CSS and JavaScript file paths,
any additional supporting assets, and default inclusion status.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(string $name, string|array|null $css, string|array|null $js, string|array|null $extras, bool $isDefault)
```

#### Parameters

- **$name**: The unique name of the library.
- **$css**: One or more relative paths to CSS files, or `null` if none.
- **$js**: One or more relative paths to JavaScript files, or `null` if none.
- **$extras**: One or more additional asset paths (e.g., fonts, maps, localization files), or `null` if none.
- **$isDefault**: Indicates whether this library is marked to be included by default.

---

### Name

Returns the unique name of the library.

#### Syntax

```php
public function Name(): string
```

#### Return Value

The name of the library.

---

### Css

Returns an array of CSS file paths associated with this library.

#### Syntax

```php
public function Css(): string[]
```

#### Return Value

The list of CSS file paths (relative or absolute).

---

### Js

Returns an array of JavaScript file paths associated with this library.

#### Syntax

```php
public function Js(): string[]
```

#### Return Value

The list of JavaScript file paths (relative or absolute).

---

### Extras

Returns an array of extra resources associated with this library.

These may include fonts, source maps, localization files, or other
supplementary files needed at runtime or during deployment.

#### Syntax

```php
public function Extras(): string[]
```

#### Return Value

The list of extra asset paths (relative or absolute).

---

### IsDefault

Indicates whether the library is included by default.

#### Syntax

```php
public function IsDefault(): bool
```

#### Return Value

Returns `true` if the library is marked as default in the manifest, `false` otherwise.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
