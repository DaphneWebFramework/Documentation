# AccountRoleDeletionHook

Hook for removing role records during account deletion.

## Methods

### OnDeleteAccount

Deletes all role records associated with the given account.

This method must be called inside a transaction to avoid an inconsistent
state in case of failure during cascading deletions.

#### Syntax

```php
public function OnDeleteAccount(\Peneus\Model\Account $account): void
```

#### Parameters

- **$account**: The account that is about to be deleted.

#### Exceptions

- **\RuntimeException**: If any role record could not be deleted.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
