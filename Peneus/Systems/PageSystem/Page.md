# Page

Represents a web page and manages its basic properties and rendering flow.

#### Example
```php
<?php
require '../../autoload.php';

use \Peneus\Systems\PageSystem\Page;

$page = (new Page(__DIR__))
    ->SetTitle('Home')
    ->SetMasterPage('basic')
    ->AddLibrary('dataTables');
?>

<?php $page->Begin()?>
    <h1>Welcome to my website</h1>
    <p>This is the home page.</p>
<?php $page->End()?>
```

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(string $directory, \Peneus\Systems\PageSystem\AccessPolicies\IAccessPolicy $accessPolicy = null, ?\Peneus\Systems\PageSystem\Renderer $renderer = null, ?\Peneus\Systems\PageSystem\LibraryManager $libraryManager = null, ?\Peneus\Systems\PageSystem\PageManifest $pageManifest = null, ?\Peneus\Systems\PageSystem\MetaCollection $metaCollection = null)
```

#### Parameters

- **$directory**: The absolute path to the directory where the page's `index.php` file is located. Typically, the `__DIR__` constant is used to specify this path.
- **$accessPolicy**: (Optional) The access policy to enforce. If not specified, the `AnyonePolicy` is used, allowing access to all users.
- **$renderer**: (Optional) The renderer to use. If not specified, a default instance is created.
- **$libraryManager**: (Optional) The library manager to use. If not specified, a default instance is created.
- **$pageManifest**: (Optional) The page manifest to use. If not specified, a default instance is created.
- **$metaCollection**: (Optional) The meta collection to use. If not specified, a default instance is created.

---

### Id

Returns the unique identifier of the page.

This corresponds to the name of the subdirectory under `pages/` where the
page's `index.php`, `manifest.json`, and related files reside.

> This method is intended to support the renderer and is typically not
required in page-level code.

#### Syntax

```php
public function Id(): string
```

#### Return Value

The page identifier (e.g., `'home'`, `'login'`, `'about'`).

---

### SetTitle

Sets the page title.

#### Syntax

```php
public function SetTitle(string $title): self
```

#### Parameters

- **$title**: The title of the page. It will be substituted into the title template when the final page title is generated.

#### Return Value

The current instance.

#### See Also

- [`SetTitleTemplate`](#SetTitleTemplate)
- [`Title`](#Title)

---

### SetTitleTemplate

Sets the template used to generate the final page title.

If not specified, the default template `{{Title}} | {{AppName}}` is used.

#### Syntax

```php
public function SetTitleTemplate(string $titleTemplate): self
```

#### Parameters

- **$titleTemplate**: A template string that may include placeholders such as `{{Title}}` and `{{AppName}}`.

#### Return Value

The current instance.

#### See Also

- [`SetTitle`](#SetTitle)
- [`Title`](#Title)

---

### Title

Returns the generated page title.

The returned string is produced by substituting the title (set via
`SetTitle`) and the application name (retrieved from configuration)
into the title template (set via `SetTitleTemplate`).

If the application name is empty, only the title is returned. If the
title is empty, only the application name is returned.

> This method is intended to support the renderer and is typically not
required in page-level code.

#### Syntax

```php
public function Title(): string
```

#### Return Value

The generated page title.

#### See Also

- [`SetTitle`](#SetTitle)
- [`SetTitleTemplate`](#SetTitleTemplate)

---

### SetMasterpage

Sets the masterpage used to layout the page content.

#### Syntax

```php
public function SetMasterpage(string $masterpage): self
```

#### Parameters

- **$masterpage**: The file name (without extension) of a masterpage under the `masterpages` directory (e.g. `basic`, `starter`).

#### Return Value

The current instance.

---

### Masterpage

Returns the selected masterpage name.

> This method is intended to support the renderer and is typically not
required in page-level code.

#### Syntax

```php
public function Masterpage(): string
```

#### Return Value

The masterpage name.

#### See Also

- [`SetMasterpage`](#SetMasterpage)

---

### Content

Returns the captured page content.

> This method is intended to support the renderer and is typically not
required in page-level code.

#### Syntax

```php
public function Content(): string
```

#### Return Value

The content between calls to `Begin()` and `End()`.

---

### Begin

Begins capturing the page content using output buffering.

#### Syntax

```php
public function Begin(): void
```

---

### End

Ends content capture and renders the page.

#### Syntax

```php
public function End(): void
```

---

### AddLibrary

Adds a library to the list of libraries to be included in the page.

#### Syntax

```php
public function AddLibrary(string $libraryName): self
```

#### Parameters

- **$libraryName**: The name of the library to add.

#### Return Value

The current instance.

#### Exceptions

- **\InvalidArgumentException**: If the library name does not exist in the manifest.

---

### RemoveLibrary

Removes a library from the set of included libraries.

This method can be used to exclude libraries that were automatically
included by default, or to undo a manual addition. If the library is
not currently included, the method does nothing.

#### Syntax

```php
public function RemoveLibrary(string $libraryName): self
```

#### Parameters

- **$libraryName**: The name of the library to remove.

#### Return Value

The current instance.

---

### RemoveAllLibraries

Removes all included libraries.

This method can be used to exclude all libraries that were automatically
included by default, as well as any that were added manually.

#### Syntax

```php
public function RemoveAllLibraries(): self
```

#### Return Value

The current instance.

---

### IncludedLibraries

Returns the list of libraries to be included in the page.

This list consists of all libraries that were marked as default in the
manifest or explicitly added using `AddLibrary`, and not removed using
`RemoveLibrary`. The libraries are returned in the order they appear in
the manifest.

> This method is intended to support the renderer and is typically not
required in page-level code.

#### Syntax

```php
public function IncludedLibraries(): \Harmonia\Core\CSequentialArray
```

#### Return Value

A list of `LibraryItem` instances.

---

### Manifest

Returns the page-level manifest.

This provides access to any page-specific CSS, JS, or extra assets
defined in the page's local `manifest.json` file.

> This method is intended to support the renderer and is typically not
required in page-level code.

#### Syntax

```php
public function Manifest(): \Peneus\Systems\PageSystem\PageManifest
```

#### Return Value

The associated page manifest instance.

---

### SetMeta

Adds or replaces a meta tag.

#### Syntax

```php
public function SetMeta(string $name, string $content, string $type = 'name'): self
```

#### Parameters

- **$name**: The name of the meta tag (e.g., `description`, `og:title`).
- **$content**: The content of the meta tag.
- **$type**: (Optional) The attribute type (e.g., `name`, `property`, `itemprop`). Defaults to `name`.

#### Return Value

The current instance.

---

### RemoveMeta

Removes a specific meta tag.

If the tag does not exist, the method does nothing.

#### Syntax

```php
public function RemoveMeta(string $name, string $type): self
```

#### Parameters

- **$name**: The name of the meta tag to remove (e.g., `description`, `og:title`).
- **$type**: The attribute type of the tag (e.g., `name`, `property`, `itemprop`).

#### Return Value

The current instance.

---

### RemoveAllMetas

Removes all meta tags.

#### Syntax

```php
public function RemoveAllMetas(): self
```

#### Return Value

The current instance.

---

### MetaItems

Returns the meta tag definitions.

This method guarantees that the `og:title` tag is present based on the
page's current title, unless it has been explicitly set elsewhere.

> This method is intended to support the renderer and is typically not
required in page-level code.

#### Syntax

```php
public function MetaItems(): \Harmonia\Core\CArray
```

#### Return Value

A `CArray` of meta tag groups. Each key is the type (e.g., `name`, `property`, `itemprop`) and each value is a `CArray` of tag names mapped to their contents.

---

### CsrfTokenName

Returns the CSRF token name.

This is the name of the form field that will contain the CSRF token
when submitted.

#### Syntax

```php
public function CsrfTokenName(): string
```

#### Return Value

The CSRF token name.

---

### CsrfTokenValue

Returns a uniquely generated CSRF token value.

Aside from token generation, this method also sets the CSRF cookie, which
is used to verify the token when the form is submitted.

#### Syntax

```php
public function CsrfTokenValue(): string
```

#### Return Value

The CSRF token value.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
