# Renderer

Handles the rendering of a web page using a template and an optional
masterpage.

## Methods

### __construct

Constructs a new instance by initializing the configuration, resource,
and logger.

#### Syntax

```php
public function __construct()
```

---

### Render

Renders the complete page output.

Loads the page template, replaces placeholders, and includes the
masterpage if one is configured. The final result is sent to output.

#### Syntax

```php
public function Render(\Peneus\Systems\PageSystem\Page $page): void
```

#### Parameters

- **$page**: The page instance to render.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
