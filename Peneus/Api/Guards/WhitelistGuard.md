# WhitelistGuard

A guard that verifies whether the request originates from an allowed IP
address, and blocks all other requests.

## Methods

### __construct

Constructs a new instance with a list of allowed IP addresses or CIDR
ranges.

Only IPv4 addresses are supported.

#### Syntax

```php
public function __construct(string ...$whitelist)
```

#### Parameters

- **$whitelist**: The IP addresses or CIDR ranges to allow. If no addresses are provided, no requests are allowed.

---

### Verify

Verifies whether the request originates from an allowed IP address.

#### Syntax

```php
public function Verify(): bool
```

#### Return Value

Returns `true` if the request originates from an allowed address (either exact match or within a CIDR range), otherwise `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
