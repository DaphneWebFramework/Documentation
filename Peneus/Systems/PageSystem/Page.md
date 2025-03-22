# Page

Represents a web page and manages its basic properties and rendering flow.

#### Example
```php
<?php
require '../../bootstrap.php';

use \Peneus\Systems\PageSystem\Page;

$page = (new Page)
    ->SetTitle('Home')
    ->SetMasterPage('basic');
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
public function __construct(?\Peneus\Systems\PageSystem\Renderer $renderer = null)
```

#### Parameters

- **$renderer**: (Optional) The renderer to use. If not specified, a default instance is created.

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

### Title

Returns the generated page title.

The returned string is produced by substituting the title (set via
`SetTitle`) and the application name (retrieved from configuration)
into the title template (set via `SetTitleTemplate`).

If the application name is empty, only the title is returned. If the
title is empty, only the application name is returned.

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

### Masterpage

Returns the selected masterpage name.

#### Syntax

```php
public function Masterpage(): string
```

#### Return Value

The masterpage name.

#### See Also

- [`SetMasterpage`](#SetMasterpage)

---

### Contents

Returns the captured page content.

#### Syntax

```php
public function Contents(): string
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

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
