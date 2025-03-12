# CompiledRules

Responsible for compiling and storing meta rules used for data validation.

It is utilized internally by the `Validator` class to optimize the validation
process.

## Methods

### __construct

Constructs a new instance by compiling the provided rules into meta rules.

#### Syntax

```php
public function __construct(array<string|int,string|\Closure|(string|\Closure)[]> $userDefinedRules)
```

#### Parameters

- **$userDefinedRules**: An associative array where each key represents a field, and each value is either a single rule (string or closure) or an array of rules.

#### Exceptions

- **\RuntimeException**: If an issue occurs during rule parsing.

---

### MetaRulesCollection

Retrieves the compiled meta rules collection.

#### Syntax

```php
public function MetaRulesCollection(): array<string|int,\Harmonia\Validation\IMetaRule[]>
```

#### Return Value

An associative array where each key represents a field, and each value is an array of `IMetaRule` objects that specify the validation rules for that field.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
