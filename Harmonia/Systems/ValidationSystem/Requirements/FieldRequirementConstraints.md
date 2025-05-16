# FieldRequirementConstraints

Encapsulates the constraints that determine whether a field is required.

This class processes `required` and `requiredWithout` rules from validation
metadata, organizing them into structured constraints that can be easily
checked during validation.

## Methods

### FromMetaRules

Extracts `required` and `requiredWithout` constraints from processed
validation rules.

#### Syntax

```php
public static function FromMetaRules(\Harmonia\Systems\ValidationSystem\MetaRules\IMetaRule[] $metaRules): self
```

#### Parameters

- **$metaRules**: An array of parsed meta rule objects (`IMetaRule`) representing field constraints.

#### Return Value

A `FieldRequirementConstraints` instance encapsulating extracted constraints.

#### Exceptions

- **\InvalidArgumentException**: If a `requiredWithout` rule is defined without a field name.

---

### IsRequired

Checks if the field is explicitly required.

#### Syntax

```php
public function IsRequired(): bool
```

#### Return Value

Returns `true` if the field must be present, otherwise `false`.

---

### HasRequiredWithoutFields

Checks whether the field has any mutually exclusive constraints.

#### Syntax

```php
public function HasRequiredWithoutFields(): bool
```

#### Return Value

Returns `true` if there are `requiredWithout` fields, otherwise `false`.

---

### RequiredWithoutFields

Retrieves the list of fields that affect the required status of this field.

These fields can make the current field optional if any of them exist.

#### Syntax

```php
public function RequiredWithoutFields(): string[]
```

#### Return Value

An array of mutually exclusive field names.

---

### FormatRequiredWithoutList

Formats the list of mutually exclusive fields for error messages.

#### Syntax

```php
public function FormatRequiredWithoutList(): string
```

#### Return Value

A formatted string containing mutually exclusive fields.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
