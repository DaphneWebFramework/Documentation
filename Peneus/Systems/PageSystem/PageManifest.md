# PageManifest

Loads and provides access to CSS and JavaScript asset references defined in a
page-level `manifest.json`.

**Example JSON structure:**
```json
{
  "css": ["index", "theme"],
  "js": ["Model", "View", "Controller"]
}
```

CSS and JS paths listed in the manifest may omit file extensions. In debug
mode (when the `IsDebug` configuration option is enabled), the framework will
append `.css` or `.js` automatically if no extension is present. If a file
path already includes a full extension (such as `.min.js` or `.css`), the
system uses it as-is.

In production mode (when `IsDebug` is disabled), it is assumed that the
deployer has already combined and minified all assets into `page.min.css`
and `page.min.js`, which are included instead of individual files.

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

Returns an array of CSS asset references.

#### Syntax

```php
public function Css(): string[]
```

#### Return Value

A list of paths or URLs. Each item is either a relative path (with or without extension, resolved against the page directory) or a URL (e.g., CDN links).

---

### Js

Returns an array of JavaScript asset references.

#### Syntax

```php
public function Js(): string[]
```

#### Return Value

A list of paths or URLs. Each item is either a relative path (with or without extension, resolved against the page directory) or a URL (e.g., CDN links).

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
