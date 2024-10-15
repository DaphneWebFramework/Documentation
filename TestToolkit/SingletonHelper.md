# SingletonHelper

Manages Singleton instances in tests, allowing you to back up, restore, and
modify them as needed.

## Methods

> ### BackupSingletons

Backs up the current Singleton instances.

This method saves the current state of all Singleton instances. It's
useful for preserving the Singleton state before performing operations
that might modify them.

#### Syntax

```php
public static function BackupSingletons(): \Harmonia\Patterns\Singleton[]
```

#### Return Value

An array containing the backed-up Singleton instances.

#### Exceptions

- **\RuntimeException**: If Singletons are already backed up.

> ### RestoreSingletons

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

> ### UpdateSingletons

Updates the Singleton instances.

This method allows for updating the current Singleton instances with a
new set of instances. It is primarily used in scenarios where Singleton
instances need to be modified or replaced.

As a precaution, this method throws an exception if the Singletons
haven't been backed up using BackupSingletons, to prevent accidental
loss or modification of the original instances.

#### Syntax

```php
public static function UpdateSingletons(\Harmonia\Patterns\Singleton[] $singletons): void
```

#### Parameters

- **$singletons**: An array containing the new Singleton instances to be set.

#### Exceptions

- **\RuntimeException**: If Singletons are updated without having a backup.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
