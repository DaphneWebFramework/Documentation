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

If an asset path omits a file extension, the framework appends `.css` or
`.js` automatically based on the asset type. In production mode, a `.min`
suffix is also added before the extension. If the path already specifies
a full filename with extension, it is used as-is.

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
