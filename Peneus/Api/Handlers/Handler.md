# Handler

Base class for API action handlers.

## Methods

### HandleAction

Executes an action based on the provided action name.

#### Syntax

```php
public function HandleAction(string $actionName): mixed
```

#### Parameters

- **$actionName**: The name of the action to execute.

#### Return Value

The result of the executed action.

#### Exceptions

- **\RuntimeException**: If the action cannot be created due to an unknown action name.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
