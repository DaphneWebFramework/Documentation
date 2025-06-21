# LibraryItem

Represents a single frontend library's CSS and JavaScript asset references.

Used by the library manifest loader to return parsed paths or URLs for each
library (e.g., Bootstrap, jQuery) defined in `frontend/manifest.json`.

## Methods

### __construct

Constructs a new instance with CSS and JavaScript inputs.

#### Syntax

```php
public function __construct(string|array|null $css, string|array|null $js, bool $isDefault)
```

#### Parameters

- **$css**: A string, array of strings, or `null`, representing one or more CSS paths or URLs.
- **$js**: A string, array of strings, or `null`, representing one or more JavaScript paths or URLs.
- **$isDefault**: Indicates whether the library is marked as default in the manifest.

---

### Css

Returns an array of CSS asset references.

#### Syntax

```php
public function Css(): string[]
```

#### Return Value

A list of paths or URLs. Each item is either a relative path (with or without extension, resolved against the frontend directory) or a URL (e.g., CDN links).

---

### Js

Returns an array of JavaScript asset references.

#### Syntax

```php
public function Js(): string[]
```

#### Return Value

A list of paths or URLs. Each item is either a relative path (with or without extension, resolved against the frontend directory) or a URL (e.g., CDN links).

---

### IsDefault

Indicates whether the library is marked as default in the manifest.

#### Syntax

```php
public function IsDefault(): bool
```

#### Return Value

Returns `true` if the library should be included by default, `false` otherwise.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
