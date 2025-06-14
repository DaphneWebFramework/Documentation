# LanguageService

Provides language-related utilities.

## Methods

### CurrentLanguage

Returns the currently configured language code.

#### Syntax

```php
public function CurrentLanguage(): string
```

#### Return Value

The language code, such as "en" for English, "tr" for Turkish, etc. Defaults to "en" if no language is configured.

---

### Languages

Returns the list of supported languages.

#### Syntax

```php
public function Languages(): array<string,string>
```

#### Return Value

An associative array of display name to language code mappings, such as `["English" => "en", "Türkçe" => "tr"]`. Returns an empty array if no languages are configured.

---

### IsSupported

Determines whether the given language code is supported.

#### Syntax

```php
public function IsSupported(string $languageCode): bool
```

#### Parameters

- **$languageCode**: A language code such as "en" or "tr".

#### Return Value

Returns `true` if the language is among the configured supported codes. Otherwise, returns `false`.

---

### CsrfTokenValue

Generates a new CSRF token value and stores its hash in a cookie.

This is typically used in client-side requests that require CSRF
protection.

#### Syntax

```php
public function CsrfTokenValue(): string
```

#### Return Value

The CSRF token to send with the request.

---

### CreateTokenGuard

Creates a token guard for validating CSRF token integrity.

This guard is intended to be used by API handlers that perform
language-related operations requiring CSRF protection.

#### Syntax

```php
public function CreateTokenGuard(): \Peneus\Api\Guards\TokenGuard
```

#### Return Value

A guard instance that encapsulates token and cookie validation logic.

---

### ReadFromCookie

Reads the language code from the cookie and invokes the callback.

If a valid language code is found in the language cookie, the given
callback will be executed with the language code. If the cookie is
missing or contains an unsupported value, it will be ignored or deleted.

#### Syntax

```php
public function ReadFromCookie(callable $onSuccess): void
```

#### Parameters

- **$onSuccess**: A callback to execute if a valid language code is found. It receives the code as a string.

---

### WriteToCookie

Writes the given language code to the language cookie.

#### Syntax

```php
public function WriteToCookie(string $languageCode, bool $strict = true): void
```

#### Parameters

- **$languageCode**: The language code to persist, e.g. "en".
- **$strict**: (Optional) Whether to validate the language code before setting the cookie. Defaults to `true`.

#### Exceptions

- **\InvalidArgumentException**: If `$strict` is `true` and the language code is not supported.

---

### DeleteCsrfCookie

Deletes the CSRF cookie.

This is typically called after the CSRF token has been verified and the
cookie is no longer needed.

#### Syntax

```php
public function DeleteCsrfCookie(): void
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
