# PendingAccount

Temporarily stores user registration data until account activation.

When a user registers, their information is stored here until they activate
their account via the email verification link. Upon activation, the data is
migrated to the `account` table and the pending record is removed.

```sql
CREATE TABLE `pendingaccount` (
  `id` INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  `email` TEXT NOT NULL,
  `passwordHash` TEXT NOT NULL,
  `displayName` TEXT NOT NULL,
  `activationCode` TEXT NOT NULL,
  `timeRegistered` DATETIME NOT NULL
) ENGINE = InnoDB;
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
