# Account

Represents a user account.

```sql
CREATE TABLE `account` (
  `id` INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  `email` TEXT NOT NULL,
  `passwordHash` TEXT NOT NULL,
  `displayName` TEXT NOT NULL,
  `timeActivated` DATETIME NOT NULL,
  `timeLastLogin` DATETIME NULL
) ENGINE = InnoDB;
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
