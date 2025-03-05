# Session

Manages PHP session lifecycle and data access.

## Methods

### Start

Starts a new session or resumes an existing one.

If session support is disabled or the session is already started, this
method does nothing.

#### Syntax

```php
public function Start(): self
```

#### Return Value

The current instance.

#### Exceptions

- **\RuntimeException**: If starting the session or regenerating the session ID fails.

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

### Set

Sets a session variable.

If the session is not started, this method does nothing.

#### Syntax

```php
public function Set(string $key, mixed $value): self
```

#### Parameters

- **$key**: The name of the session variable.
- **$value**: The value of the session variable.

#### Return Value

The current instance.

---

### Get

Retrieves a session variable.

If the session is not started, this method returns the default value.

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

If the session is not started, this method does nothing.

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

Clears all session variables.

If the session is not started, this method does nothing.

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

If the session is not started, this method does nothing.

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
