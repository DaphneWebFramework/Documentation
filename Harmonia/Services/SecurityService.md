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

Generates a cryptographically secure random token of a given byte length.

#### Syntax

```php
public function GenerateToken(int $byteLength = 32): string
```

#### Parameters

- **$byteLength**: (Optional) The number of bytes to generate. Defaults to 32.

#### Return Value

A hexadecimal string representing the random bytes. Since each byte is encoded as two hexadecimal characters, the resulting string length is exactly twice the specified byte length.

---

### TokenPattern

Returns a regular expression pattern for validating tokens of a given
byte length.

#### Syntax

```php
public static function TokenPattern(int $byteLength = 32): string
```

#### Parameters

- **$byteLength**: (Optional) The number of bytes to validate. Defaults to 32.

#### Return Value

A regular expression that matches hexadecimal strings of the appropriate length. Because each byte corresponds to two hexadecimal characters, the pattern enforces a string length of twice the specified byte length.

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

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
