# SingletonHelper

Manages Singleton instances in tests, allowing you to back up, restore, and
modify them as needed.

## Methods

### BackupSingletons

Backs up the current Singleton instances.

This method saves the current state of all Singleton instances. It's
useful for preserving the Singleton state before performing operations
that might modify them.

#### Syntax

```php
public static function BackupSingletons(): array<string,\Harmonia\Patterns\Singleton>
```

#### Return Value

An associative array containing the backed-up Singleton instances, where the keys are class names (strings) and the values are instances of the `Singleton` subclass.

#### Exceptions

- **\RuntimeException**: If Singletons are already backed up.

---

### RestoreSingletons

Restores Singleton instances from the backup.

This method resets the Singleton instances to their state when the backup
was made using BackupSingletons. This is typically used to revert
Singletons to a known state after testing or other operations that may
have altered them.

#### Syntax

```php
public static function RestoreSingletons(): void
```

#### Exceptions

- **\RuntimeException**: If no Singleton backup is found.

---

### UpdateSingletons

Updates the Singleton instances.

This method allows for updating the current Singleton instances with a
new set of instances. It is primarily used in scenarios where Singleton
instances need to be modified or replaced.

As a precaution, this method throws an exception if the Singletons
haven't been backed up using BackupSingletons, to prevent accidental
loss or modification of the original instances.

#### Syntax

```php
public static function UpdateSingletons(array<string,\Harmonia\Patterns\Singleton> $singletons): void
```

#### Parameters

- **$singletons**: An associative array containing the new subclass instances to be set, where the keys are class names (strings) and the values are instances of the `Singleton` subclass.

#### Exceptions

- **\RuntimeException**: If Singletons are updated without having a backup.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
