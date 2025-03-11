# RuleFactory

Factory class responsible for creating and managing rule objects.

Implements the Flyweight pattern to optimize memory usage by sharing
identical rule objects instead of creating new ones for each validation
request.

## Methods

### Create

Creates or retrieves a rule object based on the given rule name.

#### Syntax

```php
public static function Create(string $ruleName): ?\Harmonia\Validation\Rules\Rule
```

#### Parameters

- **$ruleName**: The name of the desired rule.

#### Return Value

Returns the rule object associated with the given name, or `null` if the rule doesn't exist.

#### Exceptions

- **\InvalidArgumentException**: When the provided rule name is an empty string.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
