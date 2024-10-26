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

- **\ValueError**: If the encoding is invalid when operating in multibyte mode.

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

- **\ValueError**: If the encoding is invalid when operating in multibyte mode.

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

- **\ValueError**: If the encoding is invalid when operating in multibyte mode.

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

- **\ValueError**: If the encoding is invalid when operating in multibyte mode.

---

### SetAt

Sets the character at the specified offset.

#### Syntax

```php
public function SetAt(int $offset, string $character): \Harmonia\Core\CString
```

#### Parameters

- **$offset**: The zero-based offset where the character will be set. If the offset is negative, no changes will be made. If the offset is greater than or equal to the length of the string, the method pads the string with spaces up to the specified offset and inserts the character at that position.
- **$character**: The character to set at the specified offset. If more than one character is provided, only the first character will be used.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If the encoding is invalid when operating in multibyte mode.

---

### DeleteAt

Deletes the character at the specified offset.

#### Syntax

```php
public function DeleteAt(int $offset): \Harmonia\Core\CString
```

#### Parameters

- **$offset**: The zero-based offset where the character will be deleted. If the offset is negative or greater than or equal to the length of the string, no changes will be made.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If the encoding is invalid when operating in multibyte mode.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
