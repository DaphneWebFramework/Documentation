# Validator

Validates data against a predefined set of validation rules.

## Methods

### __construct

Constructs a new instance with a set of user-defined validation rules.

#### Examples

```php
$validator = new Validator([
    'id' => ['required', 'integer', 'min:1'],
    'token' => 'regex:/^[a-f0-9]{64}$/',
    'countryCode' => function($value) {
        return \in_array($value, ['US', 'CA', 'MX']);
    }
]);
```
```php
$validator = new Validator([
    'username' => ['required', 'string', 'minLength:3'],
    'email' => ['required', 'email'],
    'rememberMe' => ['required', function($value) {
        return 'on' === $value || 'off' === $value;
    }]
]);
```
```php
$validator = new Validator(
    [
        'coordinates.latitude' => ['numeric', 'min:-90', 'max:90'],
        'coordinates.longitude' => ['numeric', 'min:-180', 'max:180']
    ],
    [
        'coordinates.latitude.min' => 'Latitude must be at least -90 degrees.',
        'coordinates.latitude.max' => 'Latitude cannot exceed 90 degrees.',
        'coordinates.longitude.min' => 'Longitude must be at least -180 degrees.',
        'coordinates.longitude.max' => 'Longitude cannot exceed 180 degrees.'
    ]
);
```

#### Syntax

```php
public function __construct(array<string|int,string|\Closure|(string|\Closure)[]> $userDefinedRules, ?array<string,string> $customMessages = null)
```

#### Parameters

- **$userDefinedRules**: An associative array where each key represents a field, and each value is either a single rule (string or closure) or an array of rules.
- **$customMessages**: (Optional) An associative array mapping 'field.rule' keys to custom error messages.

#### Exceptions

- **\RuntimeException**: If an error occurs while compiling the rules.

---

### Validate

Validates the provided data against the compiled rules.

#### Syntax

```php
public function Validate(array|object $data): \Harmonia\Validation\DataAccessor
```

#### Parameters

- **$data**: The data to validate, provided as an array or an object. If the data is an instance of `CArray`, it is converted to an array.

#### Return Value

Returns a data accessor object that provides access to the validated data fields.

#### Exceptions

- **\InvalidArgumentException**: If a `requiredWithout` rule is defined without a field name, or if the field references itself as a `requiredWithout` field.
- **\RuntimeException**: If the field fails any requirement rule. This includes cases where a required field is missing, the field and any mutually exclusive field are both present, or neither the field nor any mutually exclusive fields are present.
- **\RuntimeException**: If the rule does not exist or validation fails.
- **\RuntimeException**: If the user-defined closure returns `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
