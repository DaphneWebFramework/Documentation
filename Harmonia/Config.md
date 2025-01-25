# Config

Provides structured access to configuration options.

## Methods

### GetOptionsFilePath

Retrieves the path to the configuration options file.

#### Syntax

```php
public function GetOptionsFilePath(): ?\Harmonia\Core\CPath
```

#### Return Value

The path to the configuration options file, or `null` if no file is loaded.

---

### GetOptions

Retrieves configuration options.

#### Syntax

```php
public function GetOptions(): ?\Harmonia\Core\CArray
```

#### Return Value

The configuration options, or `null` if no options are loaded.

---

### Load

Loads configuration options from the specified file.

#### Syntax

```php
public function Load(\Harmonia\Core\CPath $optionsFilePath): void
```

#### Parameters

- **$optionsFilePath**: The path to the configuration options file.

#### Exceptions

- **\InvalidArgumentException**: If the specified file does not exist.

---

### Reload

Reloads configuration options from the file.

#### Syntax

```php
public function Reload(): void
```

#### Exceptions

- **\RuntimeException**: If no configuration options file is loaded.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
