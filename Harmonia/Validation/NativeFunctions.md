# NativeFunctions

## Methods

### IsNumeric

Determines if the given value is of a numeric type.

#### Syntax

```php
public function IsNumeric(mixed $value): bool
```

#### Parameters

- **$value**: The value to check.

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

- **$value**: The value to check.

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

- **$value**: The value to check.

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

- **$value**: The value to check.

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

- **$value**: The value to check.

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

- **$value**: The value to check.

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

- **$value**: The value to be matched against the regular expression.
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

- **$value**: The date/time string to be validated.
- **$param**: The format string that the date/time should adhere to, as per `DateTime::createFromFormat` documentation.

#### Return Value

Returns `true` if `$value` matches the format specified in `$param`, `false` otherwise.

#### See Also

- [https://www.php.net/manual/en/datetime.formats.php](https://www.php.net/manual/en/datetime.formats.php)

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
