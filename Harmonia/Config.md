# Config

Provides structured access to configuration options.

## Methods

### Load

Loads configuration options from the specified file.

#### Syntax

```php
public function Load(string $optionsFilePath): void
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

### Option

Retrieves the value of a configuration option.

#### Syntax

```php
public function Option(string $key): mixed
```

#### Parameters

- **$key**: The key of the configuration option.

#### Return Value

The value of the configuration option, or `null` if the key is not found.

---

### OptionOrDefault

Retrieves the value of a configuration option, or a default value if the
key does not exist.

#### Syntax

```php
public function OptionOrDefault(string $key, mixed $defaultValue): mixed
```

#### Parameters

- **$key**: The key of the configuration option.
- **$defaultValue**: The value to return if the key does not exist.

#### Return Value

The value of the configuration option, or the default value if the key is not found.

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
