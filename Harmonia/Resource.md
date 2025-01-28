# Resource

Provides access to application resources such as file system paths and URLs.

## Methods

### Initialize

Initializes the resource with the specified application path.

The application path refers to the root directory of the application.
This method is typically called in a bootstrap file (e.g., bootstrap.php
or autoload.php) using `__DIR__` to pass the root directory path.

For example:
```php
use \Harmonia\Resource;

Resource::Instance()->Initialize(__DIR__);
```

#### Syntax

```php
public function Initialize(string|\Stringable $appPath): void
```

#### Parameters

- **$appPath**: The application path to initialize with.

#### Exceptions

- **\RuntimeException**: If the resource is already initialized or the application path cannot be resolved.

---

### AppPath

Retrieves the application path.

#### Syntax

```php
public function AppPath(): \Harmonia\Core\CPath
```

#### Return Value

The application path.

#### Exceptions

- **\RuntimeException**: If the resource is not initialized.

---

### AppRelativePath

Retrieves the application's path relative to the server's root directory.

The application relative path is always returned with forward slashes
which makes it suitable for joining with both file system paths and URLs.

For example, if the server's root directory is "C:\xampp\htdocs" and the
application path is "C:\xampp\htdocs\MyProjects\CoolApp", this method will
return "MyProjects/CoolApp".

#### Syntax

```php
public function AppRelativePath(): \Harmonia\Core\CString
```

#### Return Value

The application relative path.

#### Exceptions

- **\RuntimeException**: If the resource is not initialized, the server path cannot be resolved, or the application path is not under the server path.

---

### AppUrl

Retrieves the application URL.

The application URL is formed by joining the server's root URL with the
application's relative path. The resulting URL always includes a trailing
slash to indicate a directory, ensuring compatibility with browsers and
avoiding unnecessary 301 redirects.

For example, if the server's root URL is "https://example.com" and the
application relative path is "MyProjects/CoolApp", this method will
return "https://example.com/MyProjects/CoolApp/".

#### Syntax

```php
public function AppUrl(): \Harmonia\Core\CUrl
```

#### Return Value

The application URL.

#### Exceptions

- **\RuntimeException**: If the resource is not initialized, the server path cannot be resolved, or the application path is not under the server path.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
