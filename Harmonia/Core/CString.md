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

A new `CString` instance with the leftmost characters, or an empty instance if the count is not a positive value.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

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

A new `CString` instance with the rightmost characters, or an empty instance if the count is not a positive value.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

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

A new `CString` instance with the specified middle characters, or an empty instance if the offset or count is not a positive value.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### Trim

Trims whitespace or specified characters from both sides of the string.

#### Syntax

```php
public function Trim(?string $characters = null): \Harmonia\Core\CString
```

#### Parameters

- **$characters**: (Optional) Characters to trim. Defaults to trimming whitespace characters.

#### Return Value

A new `CString` instance with the trimmed string.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### TrimLeft

Trims whitespace or specified characters from the start (left) of the
string.

#### Syntax

```php
public function TrimLeft(?string $characters = null): \Harmonia\Core\CString
```

#### Parameters

- **$characters**: (Optional) Characters to trim. Defaults to trimming whitespace characters.

#### Return Value

A new `CString` instance with the trimmed string.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### TrimRight

Trims whitespace or specified characters from the end (right) of the
string.

#### Syntax

```php
public function TrimRight(?string $characters = null): \Harmonia\Core\CString
```

#### Parameters

- **$characters**: (Optional) Characters to trim. Defaults to trimming whitespace characters.

#### Return Value

A new `CString` instance with the trimmed string.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### Lowercase

Converts the string to lowercase.

#### Syntax

```php
public function Lowercase(): \Harmonia\Core\CString
```

#### Return Value

A new `CString` instance with all characters converted to lowercase.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### Uppercase

Converts the string to uppercase.

#### Syntax

```php
public function Uppercase(): \Harmonia\Core\CString
```

#### Return Value

A new `CString` instance with all characters converted to uppercase.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### Equals

Checks if this string is equal to another string.

#### Syntax

```php
public function Equals(string|\Harmonia\Core\CString $other, bool $caseSensitive = true): bool
```

#### Parameters

- **$other**: The string to compare with.
- **$caseSensitive**: (Optional) Whether the comparison should be case-sensitive. By default, it is case-sensitive.

#### Return Value

Returns `true` if the strings are equal, `false` otherwise.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### StartsWith

Checks if the string starts with the specified search string.

#### Syntax

```php
public function StartsWith(string $searchString, bool $caseSensitive = true): bool
```

#### Parameters

- **$searchString**: The string to check if the instance starts with it.
- **$caseSensitive**: (Optional) Whether the comparison should be case-sensitive. By default, it is case-sensitive.

#### Return Value

Returns `true` if the string starts with the given search string, `false` otherwise.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### EndsWith

Checks if the string ends with the specified search string.

#### Syntax

```php
public function EndsWith(string $searchString, bool $caseSensitive = true): bool
```

#### Parameters

- **$searchString**: The string to check if the instance ends with it.
- **$caseSensitive**: (Optional) Whether the comparison should be case-sensitive. By default, it is case-sensitive.

#### Return Value

Returns `true` if the string ends with the given search string, `false` otherwise.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### IndexOf

Finds the offset of the first occurrence of a string.

#### Syntax

```php
public function IndexOf(string $searchString, int $startOffset = 0, bool $caseSensitive = true): int|null
```

#### Parameters

- **$searchString**: The string to search for.
- **$startOffset**: (Optional) The zero-based offset from which to start the search. Defaults to 0.
- **$caseSensitive**: (Optional) Whether the comparison should be case-sensitive. By default, it is case-sensitive.

#### Return Value

The zero-based offset of the search string, or `null` if not found.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### Replace

Replaces all occurrences of a specified search string with a replacement
string.

#### Syntax

```php
public function Replace(string $searchString, string $replacement, bool $caseSensitive = true): \Harmonia\Core\CString
```

#### Parameters

- **$searchString**: The substring to search for.
- **$replacement**: The substring to replace each occurrence of the search string.
- **$caseSensitive**: (Optional) Whether the comparison should be case-sensitive. By default, it is case-sensitive.

#### Return Value

A new `CString` instance with the replacements made.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

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

### offsetExists

Checks if the offset exists within the bounds of the string.

#### Syntax

```php
public function offsetExists(mixed $offset): bool
```

#### Parameters

- **$offset**: The zero-based offset to check.

#### Return Value

Returns `true` if the offset is within the string length, `false` otherwise.

#### Exceptions

- **\InvalidArgumentException**: If the offset is not an integer or is negative.

---

### offsetGet

Returns the character at a specified offset.

#### Syntax

```php
public function offsetGet(mixed $offset): mixed
```

#### Parameters

- **$offset**: The zero-based offset of the character to return.

#### Return Value

The character at the specified offset, or an empty string if the offset is out of bounds.

#### Exceptions

- **\TypeError**: If the offset is not an integer.
- **\ValueError**: If an error occurs due to encoding.

---

### offsetSet

Sets the character at the specified offset.

#### Syntax

```php
public function offsetSet(mixed $offset, mixed $value): void
```

#### Parameters

- **$offset**: The zero-based offset where the character will be set. If the offset is negative or greater than or equal to the length of the string, no changes will be made.
- **$value**: The character to set at the specified offset. If more than one character is provided, no changes will be made.

#### Exceptions

- **\TypeError**: If the offset is not an integer or the value is not a string.
- **\ValueError**: If an error occurs due to encoding.

---

### offsetUnset

Deletes the character at the specified offset.

#### Syntax

```php
public function offsetUnset(mixed $offset): void
```

#### Parameters

- **$offset**: The zero-based offset where the character will be removed. If the offset is negative or greater than or equal to the length of the string, no changes will be made.

#### Exceptions

- **\TypeError**: If the offset is not an integer.
- **\ValueError**: If an error occurs due to encoding.

---

### getIterator

Returns an iterator for traversing each character in the string.

#### Syntax

```php
public function getIterator(): \Traversable
```

#### Return Value

An iterator yielding each character in the string.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
