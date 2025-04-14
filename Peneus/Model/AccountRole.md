# AccountRole

Represents a role assigned to an account.

```sql
CREATE TABLE `accountrole` (
  `id` INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  `accountId` INT,
  `role` INT
) ENGINE = InnoDB;
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
