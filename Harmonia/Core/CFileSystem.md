# CFileSystem

Provides file system utility methods for directory and file management.

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

### DeleteDirectory

Deletes a directory and all its contents.

This method recursively deletes all files and subdirectories within the
specified directory before removing the directory itself.

#### Syntax

```php
public function DeleteDirectory(string|\Stringable $directoryPath): bool
```

#### Parameters

- **$directoryPath**: The path of the directory to be deleted.

#### Return Value

Returns `true` if the directory and its contents are deleted successfully. Otherwise, returns `false`.

---

### DeleteFile

Deletes a file.

#### Syntax

```php
public static function DeleteFile(string|\Stringable $filePath): bool
```

#### Parameters

- **$filePath**: The path of the file to be deleted.

#### Return Value

Returns `true` on success, or `false` on failure.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
