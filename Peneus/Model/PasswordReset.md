# PasswordReset

Stores one-time password reset requests initiated by users.

```sql
CREATE TABLE `passwordreset` (
  `id` INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  `accountId` INT NOT NULL,
  `resetCode` TEXT NOT NULL,
  `timeRequested` DATETIME NOT NULL
) ENGINE = InnoDB;
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
