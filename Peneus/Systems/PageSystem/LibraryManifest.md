# LibraryManifest

Loads and provides access to metadata for all frontend libraries defined in
`manifest.json`.

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
    "js": "audiojs-1.0.1/audio",
    "*": "audiojs-1.0.1/player-graphics.gif"
  }
}
```

CSS and JS paths listed in the manifest may omit file extensions. In debug
mode (when the `IsDebug` configuration option is enabled), the framework will
append `.css` or `.js` automatically if no extension is present. For example,
the entry `"js": "lib/foo"` will resolve to `lib/foo.js`. If a file path
already includes a full extension (such as `.min.js` or `.css`), the system
uses it as-is.

In production mode (when the `IsDebug` configuration option is disabled),
the framework resolves paths to minified variants by appending `.min` before
the extension. For example, `"js": "lib/foo"` will resolve to `lib/foo.min.js`.

Unlike page-level assets, library assets are not bundled or minified by the
deployer tool. Instead, the deployer preserves the structure of the manifest
and only ensures the correct file extension is applied based on the debug
configuration.

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
