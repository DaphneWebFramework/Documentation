# SendPasswordResetAction

Handles password reset requests for accounts.

The action mitigates account enumeration by always returning the same generic
success message, even if no account exists for the given email.

## Methods

### __construct

Constructs a new instance by initializing dependencies.

#### Syntax

```php
public function __construct(\Peneus\Api\Hooks\ICaptchaHook|null $captchaHook = null)
```

#### Parameters

- **$captchaHook**: (Optional) A hook for verifying captchas.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
