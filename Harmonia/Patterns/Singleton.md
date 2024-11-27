# Singleton

Base class for implementing the Singleton design pattern.

This abstract class ensures that only one instance of any subclass exists
throughout the application. It uses a static array to store instances of
subclasses.

## Methods

### Instance

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

### ReplaceInstance

Replaces the singleton instance for the subclass.

This method replaces the current singleton instance with a new one or
resets it if `null` is provided. It is primarily intended for scenarios
like testing, dynamic configuration updates, or context-specific
overrides.

#### Syntax

```php
public static function ReplaceInstance(?self $newInstance): ?static
```

#### Parameters

- **$newInstance**: The new singleton instance to set, or `null` to reset the instance.

#### Return Value

The previous instance before replacement, or `null` if no instance existed.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
