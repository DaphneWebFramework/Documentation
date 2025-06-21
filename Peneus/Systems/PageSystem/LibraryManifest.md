# LibraryManifest

Loads and provides access to CSS and JavaScript asset references defined in
the `frontend/manifest.json` file.

**Example JSON structure:**
```json
{
  "jquery": {
    "css": "jquery-ui-1.12.1.custom/jquery-ui",
    "js": [
      "jquery-3.5.1/jquery",
      "jquery-ui-1.12.1.custom/jquery-ui"
    ],
    "default": true
  },
  "selectize": {
    "css": "selectize-0.13.6/css/selectize.bootstrap4.css",
    "js": "selectize-0.13.6/js/standalone/selectize"
  },
  "audiojs": {
    "css": "audiojs-1.0.1/audio",
    "js": "audiojs-1.0.1/audio"
  }
}
```

CSS and JS paths listed in the manifest may omit file extensions. In debug
mode (when the `IsDebug` configuration option is enabled), the framework will
append `.css` or `.js` automatically if no extension is present. If a file
path already includes a full extension (such as `.min.js` or `.css`), the
system uses it as-is.

In production mode (when `IsDebug` is disabled), if a path has no extension,
the framework attempts to resolve it to a `.min.js` or `.min.css` version.
If the path already ends with a full extension, it is used as-is.

## Methods

### __construct

Constructs a new instance by loading the JSON file.

#### Syntax

```php
public function __construct()
```

#### Exceptions

- **\RuntimeException**: If the file cannot be opened, read, decoded, or validated.

---

### Items

Returns all libraries defined in the manifest.

#### Syntax

```php
public function Items(): \Harmonia\Core\CArray
```

#### Return Value

An array of library names mapped to `LibraryItem` instances. The items are ordered according to their declaration in the manifest file.

---

### Defaults

Returns the names of libraries marked as default in the manifest.

#### Syntax

```php
public function Defaults(): \Harmonia\Core\CSequentialArray
```

#### Return Value

A sequential array of library names.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
