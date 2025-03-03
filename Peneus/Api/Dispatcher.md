# Dispatcher

Dispatches API requests to the appropriate handler.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct()
```

---

### DispatchRequest

Dispatches the request to the appropriate handler.

The request must include `handler` and `action` query parameters. If a
handler cannot be found, the action is unknown, or another error occurs
during execution, the response body will contain a JSON-formatted string
with an `error` property. Otherwise, the response body will contain the
action result as a JSON-formatted string.

This method does not send the response. The final response is sent
in `OnShutdown`.

#### Syntax

```php
public function DispatchRequest(): void
```

#### See Also

- [`OnShutdown`](#OnShutdown)

---

### OnShutdown

Handles system shutdown events and ensures a response is sent.

If an error occurs during execution, the response collected by
`DispatchRequest` is replaced with an error response. Otherwise,
the existing response is sent as is.

#### Syntax

```php
public function OnShutdown(?string $errorMessage): void
```

#### Parameters

- **$errorMessage**: The error message if an error occurred, or `null` otherwise.

#### See Also

- [`DispatchRequest`](#DispatchRequest)

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
