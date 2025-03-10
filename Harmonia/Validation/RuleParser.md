# RuleParser

Parses validation rules into components (name and parameter).

## Methods

### Parse

Parses a rule string into its name and optional parameter.

#### Syntax

```php
public static function Parse(string $rule): array{: string, : ?string}
```

#### Parameters

- **$rule**: The rule string (e.g., `'min:10'` or `'required'`).

#### Return Value

The first element is the rule name. The second element is the optional rule parameter (`null` if absent).

#### Exceptions

- **\InvalidArgumentException**: If the rule is empty or contains only whitespace.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
