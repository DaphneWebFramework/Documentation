# Resource

Provides additional resources specific to the Peneus library.

This class uses composition to wrap `Harmonia\Resource`, allowing Peneus to
extend resource functionality without inheriting from it. This design avoids
the "singleton inheritance trap", which can lead to initialization conflicts
when both base and subclass maintain separate singleton instances.

## Methods

### __call

Delegates unknown method calls to the base resource.

This enables consumers of `Peneus\Resource` to transparently access all
public methods of `Harmonia\Resource`, simulating inheritance through
composition without requiring explicit method forwarding.

#### Syntax

```php
public function __call(string $method, array $arguments): mixed
```

#### Parameters

- **$method**: The method name being called.
- **$arguments**: The arguments passed to the method.

#### Return Value

The result of the delegated method call.

#### Exceptions

- **\Error**: If the method does not exist on the base resource.

---

### TemplateFilePath

Returns the absolute path to the specified template file.

#### Syntax

```php
public function TemplateFilePath(string $templateName): \Harmonia\Core\CPath
```

#### Parameters

- **$templateName**: The name of the template file without the extension.

#### Return Value

The absolute path to the template file.

---

### MasterpageFilePath

Returns the absolute path to the specified masterpage file.

#### Syntax

```php
public function MasterpageFilePath(string $masterpageName): \Harmonia\Core\CPath
```

#### Parameters

- **$masterpageName**: The name of the masterpage file without the extension.

#### Return Value

The absolute path to the masterpage file.

---

### FrontendManifestFilePath

Returns the absolute path to the frontend manifest file.

#### Syntax

```php
public function FrontendManifestFilePath(): \Harmonia\Core\CPath
```

#### Return Value

The absolute path to the frontend manifest file.

---

### FrontendLibraryFileUrl

Returns the URL to a frontend library file.

This method appends a cache-busting query parameter to the URL, based on
the file's modification time.

#### Syntax

```php
public function FrontendLibraryFileUrl(string $relativePath): \Harmonia\Core\CUrl
```

#### Parameters

- **$relativePath**: The path relative to the frontend directory, e.g., `'bootstrap/css/bootstrap'`.

#### Return Value

The URL to the file with a cache-busting query parameter.

---

### PagePath

Returns the absolute path to a page directory.

#### Syntax

```php
public function PagePath(string $pageId): \Harmonia\Core\CPath
```

#### Parameters

- **$pageId**: The identifier (folder name) of the page, e.g., `'home'`.

#### Return Value

The absolute path to the page directory.

---

### PageUrl

Returns the URL to a page directory.

This method ensures that the resulting URL ends with a trailing slash,
which helps avoid unnecessary 301 redirects in web browsers.

#### Syntax

```php
public function PageUrl(string $pageId): \Harmonia\Core\CUrl
```

#### Parameters

- **$pageId**: The identifier (folder name) of the page, e.g., `'home'`.

#### Return Value

The URL to the page directory.

---

### LoginPageUrl

Returns the URL to the login page.

This method appends a "redirect" query parameter to the URL, pointing
to the current request URI.

#### Syntax

```php
public function LoginPageUrl(): \Harmonia\Core\CUrl
```

#### Return Value

The URL to the login page with a "redirect" query parameter.

---

### PageFilePath

Returns the absolute path to a file within a page directory.

#### Syntax

```php
public function PageFilePath(string $pageId, string $relativePath): \Harmonia\Core\CPath
```

#### Parameters

- **$pageId**: The identifier (folder name) of the page, e.g., `'home'`.
- **$relativePath**: The path relative to the page directory, e.g., `'style.css'`.

#### Return Value

The absolute path to the file.

---

### PageFileUrl

Returns the URL to a file within a page directory.

This method appends a cache-busting query parameter to the URL, based on
the file's modification time.

#### Syntax

```php
public function PageFileUrl(string $pageId, string $relativePath): \Harmonia\Core\CUrl
```

#### Parameters

- **$pageId**: The identifier (folder name) of the page, e.g., `'home'`.
- **$relativePath**: The path relative to the page directory, e.g., `'style.css'`.

#### Return Value

The URL to the file with a cache-busting query parameter.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
