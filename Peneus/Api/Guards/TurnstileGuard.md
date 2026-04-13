# TurnstileGuard

A guard that verifies the Cloudflare Turnstile captcha provided in the
request.

## Methods

### __construct

Constructs a new instance by initializing dependencies.

#### Syntax

```php
public function __construct(?\Harmonia\Http\Client $client = null)
```

#### Parameters

- **$client**: (Optional) The HTTP client to use. If not provided, a new default instance is created.

---

### Verify

Verifies the Turnstile captcha token.

#### Syntax

```php
public function Verify(): bool
```

#### Return Value

Returns `true` if the verification is successful, otherwise `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
