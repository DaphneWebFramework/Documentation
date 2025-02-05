# Session

Manages PHP session lifecycle and data access.

## Methods

### IsStarted

Checks whether a session has been started.

#### Syntax

```php
public function IsStarted(): bool
```

#### Return Value

Returns `true` if the session has been started, `false` otherwise.

---

### Name

Retrieves the current session name.

The session name is used as the cookie name for storing the session ID.

#### Syntax

```php
public function Name(): string
```

#### Return Value

The current session name.

#### Exceptions

- **\RuntimeException**: If retrieving the session name fails.

---

### Start

Starts a new session or resumes an existing one.

#### Syntax

```php
public function Start(): void
```

#### Exceptions

- **\RuntimeException**: If starting the session fails.

---

### Close

Saves session data and closes the session.

#### Syntax

```php
public function Close(): void
```

#### Exceptions

- **\RuntimeException**: If writing and closing the session fails.

---

### Set

Sets a session variable.

#### Syntax

```php
public function Set(string $key, mixed $value): void
```

#### Parameters

- **$key**: The name of the session variable.
- **$value**: The value of the session variable.

---

### Get

Retrieves a session variable.

#### Syntax

```php
public function Get(string $key, mixed $defaultValue = null): mixed
```

#### Parameters

- **$key**: The name of the session variable.
- **$defaultValue**: (Optional) The default value to return if the session variable does not exist. Defaults to `null`.

#### Return Value

The value of the session variable if it exists, the default value otherwise.

---

### Remove

Removes a session variable.

#### Syntax

```php
public function Remove(string $key): void
```

#### Parameters

- **$key**: The name of the session variable.

---

### Clear

Clears all session variables.

#### Syntax

```php
public function Clear(): void
```

#### Exceptions

- **\RuntimeException**: If clearing session data fails.

---

### Destroy

Destroys the current session.

This method clears session data and completely destroys the session.
Before calling this method, ensure that the session cookie is deleted
using `Name()` to retrieve the session cookie name.

#### Syntax

```php
public function Destroy(): void
```

#### Exceptions

- **\RuntimeException**: If destroying the session fails.

#### See Also

- [`Name`](#Name)

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
