# Singleton

Base class for implementing the Singleton design pattern.

This abstract class ensures that only one instance of any subclass exists
throughout the application. It uses a static array to store instances of
subclasses.

## Methods

> ### Instance

Returns the singleton instance of the subclass.

This static method ensures that a single instance of a `Singleton`
subclass exists. It creates a new instance if one doesn't exist, or
returns the existing instance otherwise.

#### Syntax

```php
public static function Instance(): static
```

#### Return Value

The singleton instance of the subclass.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
