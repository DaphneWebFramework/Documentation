# AccountRoleDeletionHook

Hook for removing role associations during account deletion.

## Methods

### OnDeleteAccount

Deletes all records related to the account's assigned roles.

#### Syntax

```php
public function OnDeleteAccount(\Peneus\Model\Account $account): void
```

#### Parameters

- **$account**: The account that is about to be deleted.

#### Exceptions

- **\RuntimeException**: If any role entry could not be deleted.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
