# Singleton

Base class for implementing Singleton design pattern.

This abstract class provides the basic mechanism to ensure that only one
instance of a subclass exists throughout the application. It uses a static
array to store instances of subclasses.

## Methods

> ### GetInstance

Returns the singleton instance of the subclass.

This static method manages the instantiation of `Singleton` subclasses.
It creates a new instance if one doesn't already exist and returns the
existing instance if it does.

#### Syntax

```php
public static function GetInstance(): static
```

#### Return Value

The singleton instance of the subclass.

> ### __wakeup

Prevents unserialization of the instance.

#### Syntax

```php
public function __wakeup(): mixed
```

#### Exceptions

- **\RuntimeException**: If a `Singleton` instance is attempted to be unserialized. This prevents the creation of multiple instances via unserialization.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
