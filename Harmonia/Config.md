# Config

Provides structured access to configuration options.

## Methods

### GetOptions

Retrieves the configuration options.

#### Syntax

```php
public function GetOptions(): \Harmonia\Core\CArray
```

#### Return Value

The configuration options.

---

### GetOptionsFilePath

Retrieves the path to the configuration options file.

#### Syntax

```php
public function GetOptionsFilePath(): ?\Harmonia\Core\CPath
```

#### Return Value

The path to the configuration options file, or `null` if no file is loaded.

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

### GetOption

Retrieves the value of a configuration option.

#### Syntax

```php
public function GetOption(string $key): mixed
```

#### Parameters

- **$key**: The key of the configuration option.

#### Return Value

The value of the configuration option, or `null` if the key is not found.

---

### SetOption

Sets the value of a configuration option.

#### Syntax

```php
public function SetOption(string $key, mixed $value): void
```

#### Parameters

- **$key**: The key of the configuration option.
- **$value**: The value of the configuration option.

#### Exceptions

- **\RuntimeException**: If the specified key is not found or if the value type does not match the existing value type.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
