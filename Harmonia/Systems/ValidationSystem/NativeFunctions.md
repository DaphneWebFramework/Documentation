# NativeFunctions

Provides thin wrappers for native PHP functions to validate various data types.

This ensures a unified interface for validation while keeping logic minimal
and testable, without adding extra behavior beyond the underlying PHP functions.

## Methods

### IsInteger

Determines if the given value is of integer type.

#### Syntax

```php
public function IsInteger(mixed $value): bool
```

#### Parameters

- **$value**: The value to check for integer type.

#### Return Value

Returns `true` if the value is an integer, `false` otherwise.

---

### IsNumeric

Determines if the given value is of a numeric type.

#### Syntax

```php
public function IsNumeric(mixed $value): bool
```

#### Parameters

- **$value**: The value to check for numeric type.

#### Return Value

Returns `true` if the value is numeric, `false` otherwise.

---

### IsString

Determines if the given value is of string type.

#### Syntax

```php
public function IsString(mixed $value): bool
```

#### Parameters

- **$value**: The value to check for string type.

#### Return Value

Returns `true` if the value is a string, `false` otherwise.

---

### IsIntegerLike

Determines if the given value is of integer type or a string representing
an integer.

#### Syntax

```php
public function IsIntegerLike(mixed $value): bool
```

#### Parameters

- **$value**: The value to validate as an integer or integer string.

#### Return Value

Returns `true` if the value is an integer or a string representing an integer, `false` otherwise.

---

### IsEmailAddress

Determines if the given value is a valid email address.

#### Syntax

```php
public function IsEmailAddress(mixed $value): bool
```

#### Parameters

- **$value**: The value to validate as an email address.

#### Return Value

Returns `true` if the value is a valid email address, `false` otherwise.

---

### IsArray

Determines if the given value is of array type.

#### Syntax

```php
public function IsArray(mixed $value): bool
```

#### Parameters

- **$value**: The value to check for array type.

#### Return Value

Returns `true` if the value is an array, `false` otherwise.

---

### IsUploadedFile

Determines if the given value represents an uploaded file.

#### Syntax

```php
public function IsUploadedFile(mixed $value): bool
```

#### Parameters

- **$value**: The value to validate as a file upload array.

#### Return Value

Returns `true` if the value represents an uploaded file, `false` otherwise.

---

### MatchRegex

Determines if the given value matches the pattern specified by the
parameter.

#### Syntax

```php
public function MatchRegex(string $value, string $param): bool
```

#### Parameters

- **$value**: The string value to validate against the regular expression pattern.
- **$param**: The regular expression pattern.

#### Return Value

Returns `true` if the value matches the pattern, `false` otherwise.

---

### MatchDateTime

Validates whether a specified string represents a date/time that matches
a given format.

#### Syntax

```php
public function MatchDateTime(string $value, string $param): bool
```

#### Parameters

- **$value**: The string value to validate as a date/time.
- **$param**: The format string that the date/time should adhere to, as per `DateTime::createFromFormat` documentation.

#### Return Value

Returns `true` if `$value` matches the format specified in `$param`, `false` otherwise.

#### See Also

- [https://www.php.net/manual/en/datetime.formats.php](https://www.php.net/manual/en/datetime.formats.php)

---

### IsEnumValue

Validates whether a given value is a valid case of a specified enum class.

Supports both backed and pure enums. For backed enums, the value must
match the enum's backing type exactly and exist in its defined cases.
For pure enums, the value must match the name of a defined case.

#### Syntax

```php
public function IsEnumValue(mixed $value, string $enumClass): bool
```

#### Parameters

- **$value**: The value to validate as an enum case.
- **$enumClass**: The fully qualified name of the enum class.

#### Return Value

Returns `true` if the value matches a valid enum case, `false` otherwise.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
