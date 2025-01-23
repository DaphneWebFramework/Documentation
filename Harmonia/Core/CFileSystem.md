# CFileSystem

Base class for implementing the Singleton design pattern.

This abstract class ensures that only one instance of any subclass exists
throughout the application. It uses a static array to store instances of
subclasses.

## Methods

### CreateDirectory

Creates a directory.

Returns successfully if the directory already exists.

#### Syntax

```php
public function CreateDirectory(string|\Stringable $directoryPath, int $permissions = 0755): bool
```

#### Parameters

- **$directoryPath**: The path of the directory to be created.
- **$permissions**: (Optional) Permissions to set on the created directory. Defaults to `0755`, which means the owner has full permissions, and others have read and execute permissions.

#### Return Value

Returns `true` if the directory is created successfully or it already exists. Otherwise, returns `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
