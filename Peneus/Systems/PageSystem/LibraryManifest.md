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

If an asset path omits a file extension, the framework appends `.css` or
`.js` automatically based on the asset type. In production mode, a `.min`
suffix is also added before the extension. If the path already specifies
a full filename with extension, it is used as-is.

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
