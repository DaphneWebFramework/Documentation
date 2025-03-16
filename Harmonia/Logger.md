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
- `IsDebug`: Enables debug mode. When `true`, debug messages are logged
  regardless of `LogLevel`.

#### Examples

Logging a debug message (effective only in debug mode):
```php
Logger::Instance()->Debug("Fetching user data for ID: {$userId}");
```

Logging an error:
```php
Logger::Instance()->Error('Database connection failed.');
```

Avoiding unnecessary computation in case logging is disabled:
```php
Logger::Instance()->Info(fn() => heavyComputation());
```

## Methods

### Debug

Logs a debug message.

This method writes a log entry when the `IsDebug` configuration option
is enabled. Unlike other log methods, the configured `LogLevel` does not
affect debug messages.

#### Syntax

```php
public function Debug(string|callable $message): void
```

#### Parameters

- **$message**: The debug message to log, or a callable returning the message.

---

### Info

Logs an informational message.

This method writes a log entry when the configured `LogLevel` is set to
`LEVEL_INFO` (3).

#### Syntax

```php
public function Info(string|callable $message): void
```

#### Parameters

- **$message**: The message to log, or a callable returning the message.

---

### Warning

Logs a warning message.

This method writes a log entry when the configured `LogLevel` is set to
`LEVEL_WARNING` (2) or higher.

#### Syntax

```php
public function Warning(string|callable $message): void
```

#### Parameters

- **$message**: The message to log, or a callable returning the message.

---

### Error

Logs an error message.

This method writes a log entry when the configured `LogLevel` is set to
`LEVEL_ERROR` (1) or higher.

#### Syntax

```php
public function Error(string|callable $message): void
```

#### Parameters

- **$message**: The message to log, or a callable returning the message.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
