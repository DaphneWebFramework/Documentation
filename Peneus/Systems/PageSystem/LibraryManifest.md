# LibraryManifest

Loads and provides access to metadata for all frontend libraries defined in
`manifest.json`.

**Example JSON structure:**
```json
{
  "jquery": {
    "default": true,
    "css": "jquery-ui-1.12.1.custom/jquery-ui",
    "js": [
      "jquery-3.5.1/jquery",
      "jquery-ui-1.12.1.custom/jquery-ui"
    ]
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

CSS and JS paths listed in the manifest may omit file extensions. If so, the
framework will append `.css` / `.js` or their minified equivalents (e.g.,
`.min.js`) based on the `IsDebug` configuration option.

For example, the entry `"js": "lib/foo"` becomes:
- `lib/foo.js` in development
- `lib/foo.min.js` in production

If a file path already includes a full extension (e.g., `.min.js` or `.css`),
the system uses it as-is without modification.

## Methods

### __construct

Constructs a new instance by loading the JSON file.

#### Syntax

```php
public function __construct()
```

#### Exceptions

- **\RuntimeException**: If the file cannot be read or contains invalid structure.

---

### Get

Retrieves a library item by name.

#### Syntax

```php
public function Get(string $name): ?\Peneus\Systems\PageSystem\LibraryItem
```

#### Parameters

- **$name**: The name of the library.

#### Return Value

The matching `LibraryItem`, or `null` if not found.

---

### Defaults

Retrieves all library items marked as default.

#### Syntax

```php
public function Defaults(): \Harmonia\Core\CArray<string,\Peneus\Systems\PageSystem\LibraryItem>
```

#### Return Value

A new `CArray` containing `LibraryItem` instances which are marked as default in the manifest.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
