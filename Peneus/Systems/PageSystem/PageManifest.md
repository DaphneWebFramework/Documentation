# PageManifest

Loads and provides access to metadata for assets defined in a page-level
`manifest.json`.

**Example JSON structure:**
```json
{
  "css": ["index", "theme"],
  "js": ["Model", "View", "Controller"],
  "*": "localization.json"
}
```

CSS and JS paths listed in the manifest may omit file extensions. In debug
mode (when the `IsDebug` configuration option is enabled), the framework will
append `.css` or `.js` automatically if no extension is present. For example,
the entry `"js": "View"` will resolve to `View.js`. If a file path already
includes a full extension (such as `.min.js` or `.css`), the system uses it
as-is.

In production mode (when the `IsDebug` configuration option is disabled),
unlike library assets, the page system does not resolve or append `.min`
suffixes for specific assets. Instead, it assumes the deployer tool has
already minified and combined all CSS and JavaScript files into two optimized
bundles named `page.min.css` and `page.min.js`, which are then included in
place of individual files.

## Methods

### __construct

Constructs a new instance by loading the manifest file from the page
directory.

#### Syntax

```php
public function __construct(string $pageId)
```

#### Parameters

- **$pageId**: The unique identifier of the page.

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

Returns an array of extra resources.

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
