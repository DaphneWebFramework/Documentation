# RuleParser

Parses validation rules into components (name and parameter).

## Methods

### Parse

Parses a rule string into its name and optional parameter.

#### Syntax

```php
public static function Parse(string $rule): array<int,?string>
```

#### Parameters

- **$rule**: The rule string (e.g., `'min:10'` or `'required'`).

#### Return Value

A tuple where the first element is the rule name and the second is the optional rule parameter (`null` if absent).

#### Exceptions

- **\InvalidArgumentException**: If the rule is empty or contains only whitespace.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
