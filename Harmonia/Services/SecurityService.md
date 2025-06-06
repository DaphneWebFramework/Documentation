# SecurityService

Provides security-related utilities.

## Methods

### HashPassword

Hashes a password using a secure hashing algorithm.

#### Syntax

```php
public function HashPassword(string $password): string
```

#### Parameters

- **$password**: The plaintext password.

#### Return Value

The hashed password.

---

### VerifyPassword

Verifies a plaintext password against a hashed password.

#### Syntax

```php
public function VerifyPassword(string $password, string $hash): bool
```

#### Parameters

- **$password**: The plaintext password.
- **$hash**: The hashed password for comparison.

#### Return Value

Returns `true` if the password matches the hash, otherwise `false`.

---

### GenerateToken

Generates a cryptographically secure random token.

#### Syntax

```php
public function GenerateToken(): string
```

#### Return Value

A 64-character hexadecimal token.

---

### GenerateCsrfToken

Generates a CSRF token and its hashed cookie value.

#### Syntax

```php
public function GenerateCsrfToken(): \Harmonia\Services\Security\CsrfToken
```

#### Return Value

A `CsrfToken` instance containing the token and its obfuscated hash.

---

### VerifyCsrfToken

Verifies whether a CSRF token matches its expected hash.

#### Syntax

```php
public function VerifyCsrfToken(\Harmonia\Services\Security\CsrfToken $csrfToken): bool
```

#### Parameters

- **$csrfToken**: The CSRF token instance to verify.

#### Return Value

Returns `true` if the token is valid, otherwise `false`.

---

### IsValidToken

Determines whether the given string is a valid token.

A valid token is a 64-character string composed exclusively of
lowercase hexadecimal digits (a–f, 0–9).

#### Syntax

```php
public static function IsValidToken(string $value): bool
```

#### Parameters

- **$value**: The token string to validate.

#### Return Value

Returns `true` if the string matches the expected format, `false` otherwise.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
