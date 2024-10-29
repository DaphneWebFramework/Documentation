# CString

CString is a wrapper class for string manipulation, allowing the use of both
single-byte and multibyte encodings.

This class requires PHP's `mbstring` extension for multibyte encoding support.

## Methods

### __construct

Constructs a new instance of CString.

#### Syntax

```php
public function __construct(string|\Stringable $value = '', ?string $encoding = null)
```

#### Parameters

- **$value**: The string value to store. If a `CString` instance is provided, the value, encoding, and single-byte/multibyte status are copied from the original instance.
- **$encoding**: The encoding to use (e.g., 'UTF-8', 'ISO-8859-1'). If `null`, defaults to the return value of `mb_internal_encoding`. This parameter is ignored when the `$value` is an instance of `CString`.

---

### __toString

Converts the CString instance to a string.

#### Syntax

```php
public function __toString(): string
```

#### Return Value

The string value stored in the instance.

---

### IsEmpty

Checks if the string is empty.

#### Syntax

```php
public function IsEmpty(): bool
```

#### Return Value

Returns `true` if the string is empty, `false` otherwise.

---

### Length

Returns the length of the string.

#### Syntax

```php
public function Length(): int
```

#### Return Value

The number of characters in the string.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### First

Returns the first character of the string.

#### Syntax

```php
public function First(): string
```

#### Return Value

The first character of the string, or an empty string if the string is empty.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### Last

Returns the last character of the string.

#### Syntax

```php
public function Last(): string
```

#### Return Value

The last character of the string, or an empty string if the string is empty.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### At

Returns the character at a specified offset.

#### Syntax

```php
public function At(int $offset): string
```

#### Parameters

- **$offset**: The zero-based offset of the character to return.

#### Return Value

The character at the specified offset, or an empty string if the offset is out of bounds.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### SetAt

Sets the character at the specified offset.

#### Syntax

```php
public function SetAt(int $offset, string $character): \Harmonia\Core\CString
```

#### Parameters

- **$offset**: The zero-based offset where the character will be set. If the offset is negative or greater than or equal to the length of the string, no changes will be made.
- **$character**: The character to set at the specified offset. If more than one character is provided, no changes will be made.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### InsertAt

Inserts a substring at the specified offset.

#### Syntax

```php
public function InsertAt(int $offset, string $substring): \Harmonia\Core\CString
```

#### Parameters

- **$offset**: The zero-based offset where the insertion will start. If the offset is negative or greater than the length of the string, no changes will be made.
- **$substring**: The substring to insert. If an empty string is provided, no changes will be made.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### DeleteAt

Deletes a range of characters starting from the specified offset.

#### Syntax

```php
public function DeleteAt(int $offset, int $count = 1): \Harmonia\Core\CString
```

#### Parameters

- **$offset**: The zero-based offset where the deletion will start. If the offset is negative or greater than or equal to the length of the string, no changes will be made.
- **$count**: (Optional) The number of characters to delete. If this value is less than 1, no changes will be made. If it exceeds the remaining characters, it will delete up to the end. Defaults to 1.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### Left

Extracts a specified number of characters from the left side of the
string.

#### Syntax

```php
public function Left(int $count): \Harmonia\Core\CString
```

#### Parameters

- **$count**: The number of characters to return. If greater than or equal to the length of the string, the entire string is returned.

#### Return Value

A new `CString` instance with the leftmost characters.

#### Exceptions

- **\InvalidArgumentException**: If the count is negative.

---

### Right

Extracts a specified number of characters from the right side of the
string.

#### Syntax

```php
public function Right(int $count): \Harmonia\Core\CString
```

#### Parameters

- **$count**: The number of characters to return. If greater than or equal to the length of the string, the entire string is returned.

#### Return Value

A new `CString` instance with the rightmost characters.

#### Exceptions

- **\InvalidArgumentException**: If the count is negative.

---

### Middle

Extracts a specified number of characters starting from a specified
offset in the string.

#### Syntax

```php
public function Middle(int $offset, int $count = PHP_INT_MAX): \Harmonia\Core\CString
```

#### Parameters

- **$offset**: The zero-based starting offset of the characters to return.
- **$count**: (Optional) The number of characters to return. If omitted, or if fewer characters are available in the string from the offset, only the available characters are returned.

#### Return Value

A new CString instance with the specified middle characters.

#### Exceptions

- **\InvalidArgumentException**: If either the offset or count is negative.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
