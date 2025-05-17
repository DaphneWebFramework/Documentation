# ShutdownHandler

Base class for implementing the Singleton design pattern.

This abstract class ensures that only one instance of any subclass exists
throughout the application. It uses a static array to store instances of
subclasses.

## Methods

### AddListener

Adds a listener to the shutdown process.

#### Syntax

```php
public function AddListener(\Harmonia\Systems\ShutdownSystem\IShutdownListener $listener): void
```

#### Parameters

- **$listener**: The listener to add.

---

### OnShutdown

The shutdown function that is called when the script ends.

This function calls the `OnShutdown` method of each listener and passes
an error message if an error occurred during script execution.

#### Syntax

```php
public function OnShutdown(): void
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
