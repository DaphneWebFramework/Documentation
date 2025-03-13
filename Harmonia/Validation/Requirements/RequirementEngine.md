# RequirementEngine

Processes requirement rules for a given field.

## Methods

### __construct

Constructs a new instance by extracting constraints and checking field
presence.

#### Syntax

```php
public function __construct(string|int $field, \Harmonia\Validation\MetaRules\IMetaRule[] $metaRules, \Harmonia\Validation\DataAccessor $dataAccessor)
```

#### Parameters

- **$field**: The field name or index being validated.
- **$metaRules**: An array of meta rules associated with the field.
- **$dataAccessor**: Provides access to the dataset.

#### Exceptions

- **\InvalidArgumentException**: If a `requiredWithout` rule is defined without a field name.

---

### Validate

Validates the field against requirement rules.

#### Syntax

```php
public function Validate(): void
```

#### Exceptions

- **\RuntimeException**: If the field fails any requirement rule. This includes cases where a required field is missing, the field and any mutually exclusive field are both present, or neither the field nor any mutually exclusive fields are present.

---

### ShouldSkipFurtherValidation

Determines whether further validation for the field should be skipped.

#### Syntax

```php
public function ShouldSkipFurtherValidation(): false
```

#### Return Value

If the field is present, meaning it should undergo further validation.

---

### FilterOutRequirementRules

Filters out requirement rules from a list of meta rules.

This step is essential to avoid "Unknown rule" errors during subsequent
validations in the validator.

#### Syntax

```php
public function FilterOutRequirementRules(\Harmonia\Validation\MetaRules\IMetaRule[] $metaRules): \Harmonia\Validation\MetaRules\IMetaRule[]
```

#### Parameters

- **$metaRules**: An array of meta rule objects for the field.

#### Return Value

Returns the meta rules excluding `required` and `requiredWithout` rules.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
