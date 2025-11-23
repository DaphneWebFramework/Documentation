# Assets

Represents normalized CSS and JavaScript asset references.

Used by both page-level and library-level manifest loaders to store and
return parsed paths or URLs. Input values may be strings, arrays of strings,
or `null`, and are normalized internally to consistent arrays.

## Methods

### __construct

Constructs a new instance with CSS and JavaScript inputs.

#### Syntax

```php
public function __construct(string|array|null $css = \Peneus\Systems\PageSystem\null, string|array|null $js = \Peneus\Systems\PageSystem\null)
```

#### Parameters

- **$css**: (Optional) A string, array of strings, or `null`, representing one or more CSS paths or URLs. Defaults to `null`.
- **$js**: (Optional) A string, array of strings, or `null`, representing one or more JavaScript paths or URLs. Defaults to `null`.

---

### Css

Returns an array of CSS asset references.

#### Syntax

```php
public function Css(): string[]
```

#### Return Value

A list of paths or URLs. Each item is either a relative path (with or without extension, resolved relative to its context) or a URL (e.g., CDN links).

---

### Js

Returns an array of JavaScript asset references.

#### Syntax

```php
public function Js(): string[]
```

#### Return Value

A list of paths or URLs. Each item is either a relative path (with or without extension, resolved relative to its context) or a URL (e.g., CDN links).

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
