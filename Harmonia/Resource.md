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

- **\RuntimeException**: If the resource is already initialized or the specified application path cannot be resolved.

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

The application relative path is always returned with forward slashes,
making it suitable for use in both file system paths and URLs.

**Example**: When the app is physically inside the server path
  - Server root: `C:\xampp\htdocs`
  - Application path: `C:\xampp\htdocs\MyProjects\MyApp`
  - Returns: `MyProjects/MyApp`

This method also supports cases where the application is symlinked inside
the server directory. If the application path is not physically located
under the server root, but a symbolic link inside the server directory
points to the application path, this method will correctly resolve the
link and compute the relative path accordingly.

**Example**: When the app is symlinked inside the server path
  - Server root: `/var/www/html`
  - Application path: `/home/user/projects/myapp`
  - Symlink: `/var/www/html/myapp" → "/home/user/projects/myapp`
  - Returns: `myapp`

#### Syntax

```php
public function AppRelativePath(): \Harmonia\Core\CString
```

#### Return Value

The application's relative path.

#### Exceptions

- **\RuntimeException**: If the resource is not initialized, the server path is not available or cannot be resolved, or the application path is neither under the server path nor accessible via a valid symlink inside the server directory.

---

### AppUrl

Retrieves the application URL.

The application URL is formed by joining the server's root URL with the
application's relative path. The resulting URL always includes a trailing
slash to indicate a directory, ensuring compatibility with browsers and
avoiding unnecessary 301 redirects.

**Example**:
  - Server URL: `https://example.com`
  - Application relative path: `MyProjects/MyApp`
  - Returns: `https://example.com/MyProjects/MyApp/`

#### Syntax

```php
public function AppUrl(): \Harmonia\Core\CUrl
```

#### Return Value

The application URL.

#### Exceptions

- **\RuntimeException**: If the server URL is not available, the resource is not initialized, the server path cannot be resolved, or the application path is neither under the server path nor accessible via a valid symlink inside the server directory.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
