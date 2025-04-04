# Assets

Encapsulates asset file paths such as CSS, JavaScript, and extra resources.

This class is used to represent normalized asset definitions for both
frontend libraries and individual pages. Paths may be specified as a string,
an array of strings, or `null`.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(string|array|null $css, string|array|null $js, string|array|null $extras)
```

#### Parameters

- **$css**: One or more relative paths to CSS files, or `null` if none.
- **$js**: One or more relative paths to JavaScript files, or `null` if none.
- **$extras**: One or more additional asset paths (e.g., fonts, maps, localization files), or `null` if none.

---

### Css

Returns an array of CSS file paths.

#### Syntax

```php
public function Css(): string[]
```

#### Return Value

The list of CSS file paths (relative or absolute).

---

### Js

Returns an array of JavaScript file paths.

#### Syntax

```php
public function Js(): string[]
```

#### Return Value

The list of JavaScript file paths (relative or absolute).

---

### Extras

Returns an array of extra resources associated with this asset group.

These may include fonts, source maps, or other supplementary assets
(e.g., `.woff2`, `.min.js.map`, `.min.css.map`, `.json`, `.png`) that
are required at runtime by the production version of the application
and must be copied alongside the main assets during deployment.

File paths may contain wildcard characters (e.g., `*`, `?`), which are
matched against the filesystem during deployment.

#### Syntax

```php
public function Extras(): string[]
```

#### Return Value

The list of extra asset paths (relative or absolute). Paths may include wildcard patterns (e.g., `*`, `?`).

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
