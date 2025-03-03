# HandlerRegistry

Manages the registration and retrieval of API handlers.

## Methods

### RegisterHandler

Registers a handler class by name.

#### Syntax

```php
public function RegisterHandler(string $handlerName, string $handlerClassName): void
```

#### Parameters

- **$handlerName**: The unique name of the handler.
- **$handlerClassName**: The fully qualified class name of the handler.

#### Exceptions

- **\InvalidArgumentException**: If the handler name is empty, already registered, or the class does not extend the `Handler` class.
- **\RuntimeException**: If the specified handler class does not exist.

---

### FindHandler

Finds and returns an instance of the requested handler.

#### Syntax

```php
public function FindHandler(string $handlerName): ?\Peneus\Api\Handlers\Handler
```

#### Parameters

- **$handlerName**: The name of the handler.

#### Return Value

The handler instance if found, otherwise `null`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
