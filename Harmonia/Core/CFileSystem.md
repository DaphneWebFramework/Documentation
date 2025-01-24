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
public function DeleteFile(string|\Stringable $filePath): bool
```

#### Parameters

- **$filePath**: The path of the file to be deleted.

#### Return Value

Returns `true` on success, or `false` on failure.

---

### FindFiles

Searches for files in a directory.

#### Syntax

```php
public function FindFiles(string|\Stringable $directoryPath, string $wildcard, bool $recursive = false): \Generator
```

#### Parameters

- **$directoryPath**: The path of the directory to search in.
- **$wildcard**: A string containing wildcard characters (* ?).
- **$recursive**: (Optional) If this parameter is `true`, the search is recursive, meaning it will include all subdirectories. Otherwise, only the root of the specified directory is searched. Defaults to `false`.

#### Return Value

A generator yielding `CPath` instances for each matching file.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
