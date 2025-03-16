# Logger

Logs messages to a file.

Logging behavior is controlled via configuration:
- `LogFile`: Path to the log file. A relative path is prefixed with the
  application root directory, while an absolute path is used as is.
- `LogLevel`: Controls which messages are logged:
  - `0`: Logging is disabled.
  - `1`: Logs only error messages.
  - `2`: Logs warnings and errors.
  - `3`: Logs info, warnings, and errors.

#### Examples

```php
Logger::Instance()->Info('Application started.');
```

Avoids unnecessary computation in case logging is disabled:
```php
Logger::Instance()->Info(fn() => heavyComputation());
```

## Methods

### Info

Logs an informational message.

#### Syntax

```php
public function Info(string|callable $message): void
```

#### Parameters

- **$message**: The message to log, or a callable returning the message.

---

### Warning

Logs a warning message.

#### Syntax

```php
public function Warning(string|callable $message): void
```

#### Parameters

- **$message**: The message to log, or a callable returning the message.

---

### Error

Logs an error message.

#### Syntax

```php
public function Error(string|callable $message): void
```

#### Parameters

- **$message**: The message to log, or a callable returning the message.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
