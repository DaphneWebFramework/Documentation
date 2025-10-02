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
public function TokenPattern(int $byteLength = 32): string
```

#### Parameters

- **$byteLength**: (Optional) The number of bytes to validate. Defaults to 32.

#### Return Value

A regular expression that matches hexadecimal strings of the appropriate length. Because each byte corresponds to two hexadecimal characters, the pattern enforces a string length of twice the specified byte length.

---

### GenerateCsrfPair

Creates a token and its corresponding cookie value.

Returns a token (to be included in forms or request headers) and a
matching value for storing in a cookie. Together, these values can
later be verified to help mitigate cross-site request forgery (CSRF)
attacks by ensuring the request originated from the same client.

#### Syntax

```php
public function GenerateCsrfPair(): array{0: string, 1: string}
```

#### Return Value

A two-element array containing the generated token and its corresponding cookie value.

#### See Also

- [`VerifyCsrfPair`](#VerifyCsrfPair)

---

### VerifyCsrfPair

Verifies a token against its corresponding cookie value.

Compares the provided token with the value stored in the cookie. If
they match, the request is considered authentic. This check is used
to mitigate cross-site request forgery (CSRF) attacks by validating
that the request was issued by the same client that received the token.

#### Syntax

```php
public function VerifyCsrfPair(string $token, string $cookieValue): bool
```

#### Parameters

- **$token**: The token received from the client (e.g., from a form field or request header).
- **$cookieValue**: The value retrieved from the cookie.

#### Return Value

Returns `true` if the token matches the cookie value, otherwise `false`.

#### See Also

- [`GenerateCsrfPair`](#GenerateCsrfPair)

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
