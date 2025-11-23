# SignInWithGoogleAction

Authenticates a user with Google Sign-In credentials.

If no matching account exists, it first creates a new account and then
proceeds with the sign-in. The account is created with an empty password
hash. A persistent login session is always established for the user.

## Methods

### __construct

Constructs a new instance by initializing dependencies.

#### Syntax

```php
public function __construct(?\Harmonia\Http\Client $client = \Peneus\Api\Actions\Account\null)
```

#### Parameters

- **$client**: (Optional) The HTTP client to use. If not provided, a new default instance is created.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
