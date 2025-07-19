# Session

Manages PHP session lifecycle and data access.

## Methods

### Start

Starts a new session or resumes an existing one.

If session support is disabled or the session has already been started,
this method does nothing.

#### Syntax

```php
public function Start(): self
```

#### Return Value

The current instance.

#### Exceptions

- **\RuntimeException**: If starting the session fails.

---

### RenewId

Regenerates the session ID to mitigate session fixation attacks.

This method replaces the current session ID with a new one, preserving
existing session data. It requires that the session be already started;
otherwise, it does nothing.

#### Syntax

```php
public function RenewId(): self
```

#### Return Value

The current instance.

#### Exceptions

- **\RuntimeException**: If regenerating the session ID fails.

---

### Close

Saves session data and closes the session.

If the session is not started, this method does nothing.

#### Syntax

```php
public function Close(): self
```

#### Return Value

The current instance.

#### Exceptions

- **\RuntimeException**: If writing and closing the session fails.

---

### Get

Retrieves a session variable.

This method does not require the session to be currently started; it
allows read access even after the session has been closed, as long as
the `$_SESSION` superglobal is still available.

#### Syntax

```php
public function Get(string $key, mixed $defaultValue = null): mixed
```

#### Parameters

- **$key**: The name of the session variable.
- **$defaultValue**: (Optional) The default value to return if the `$_SESSION` superglobal itself or the session variable does not exist. Defaults to `null`.

#### Return Value

The value of the session variable if available, or the default value.

---

### Set

Sets a session variable.

This method does nothing if the session has not been started, or if it
has already been closed.

#### Syntax

```php
public function Set(string $key, mixed $value): self
```

#### Parameters

- **$key**: The name of the session variable.
- **$value**: The value to assign to the session variable.

#### Return Value

The current instance.

---

### Remove

Removes a session variable.

This method does nothing if the session has not been started, or if it
has already been closed.

#### Syntax

```php
public function Remove(string $key): self
```

#### Parameters

- **$key**: The name of the session variable.

#### Return Value

The current instance.

---

### Clear

Removes all variables from the session.

This method does nothing if the session has not been started, or if it
has already been closed.

#### Syntax

```php
public function Clear(): self
```

#### Return Value

The current instance.

#### Exceptions

- **\RuntimeException**: If clearing session data fails.

---

### Destroy

Destroys the current session.

This method does nothing if the session has not been started, or if it
has already been closed.

It deletes the session cookie, clears all session variables, and deletes
the session data stored on the server.

#### Syntax

```php
public function Destroy(): self
```

#### Return Value

The current instance.

#### Exceptions

- **\RuntimeException**: If obtaining the session name fails, if HTTP headers have already been sent, if deleting the session cookie fails, if clearing session data fails, or if destroying the session fails.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
