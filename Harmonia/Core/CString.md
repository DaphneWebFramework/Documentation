# CString

CString is a wrapper for PHP's native `string` type, providing enhanced
methods for string manipulation, with support for both single-byte and
multibyte encodings.

This class requires PHP's `mbstring` extension for multibyte encoding support.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(string|\Stringable $value = '', ?string $encoding = null)
```

#### Parameters

- **$value**: (Optional) The string value to store. If omitted, defaults to an empty string. If a `CString` instance is provided, the value, encoding, and single-byte/multibyte status are copied from the original instance.
- **$encoding**: (Optional) The encoding to use (e.g., 'UTF-8', 'ISO-8859-1'). If omitted or set to `null`, defaults to the return value of `mb_internal_encoding`. This parameter is ignored when `$value` is an instance of `CString`. Note that encoding names are case-insensitive.

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

Returns the length.

#### Syntax

```php
public function Length(): int
```

#### Return Value

The number of characters.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

---

### First

Returns the first character.

#### Syntax

```php
public function First(): string
```

#### Return Value

The first character, or an empty string if the string is empty.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Last`](#Last)

---

### Last

Returns the last character.

#### Syntax

```php
public function Last(): string
```

#### Return Value

The last character, or an empty string if the string is empty.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`First`](#First)

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

The character at the specified offset, or an empty string if the offset is out of range.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`SetAt`](#SetAt)

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

#### See Also

- [`At`](#At)

---

### InsertAt

Inserts a substring at the specified offset.

#### Syntax

```php
public function InsertAt(int $offset, string $substring): \Harmonia\Core\CString
```

#### Parameters

- **$offset**: The zero-based offset where the insertion will start. If the offset is negative or greater than the length of the string, no changes will be made. If the offset equals the length, the substring will be appended.
- **$substring**: The substring to insert. If an empty string is provided, no changes will be made.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Append`](#Append)

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

### Append

Appends the specified string.

#### Syntax

```php
public function Append(string|\Harmonia\Core\CString $substring): \Harmonia\Core\CString
```

#### Parameters

- **$substring**: The string to append. If a `CString` instance is provided, its value will be used.

#### Return Value

The current instance.

#### See Also

- [`InsertAt`](#InsertAt)

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

A new `CString` instance with the leftmost characters, or an empty instance if `$count` is not positive.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Right`](#Right)
- [`Middle`](#Middle)

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

A new `CString` instance with the rightmost characters, or an empty instance if `$count` is not positive.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Left`](#Left)
- [`Middle`](#Middle)

---

### Middle

Extracts a specified number of characters starting from a specified
offset.

#### Syntax

```php
public function Middle(int $offset, int $count = PHP_INT_MAX): \Harmonia\Core\CString
```

#### Parameters

- **$offset**: The zero-based starting offset of the characters to return.
- **$count**: (Optional) The number of characters to return. If omitted, or if fewer characters are available from the offset, only the available characters are returned.

#### Return Value

A new `CString` instance with the specified middle characters, or an empty instance if `$offset` is out of range or `$count` is not positive.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Left`](#Left)
- [`Right`](#Right)

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

#### See Also

- [`TrimLeft`](#TrimLeft)
- [`TrimRight`](#TrimRight)

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

#### See Also

- [`Trim`](#Trim)
- [`TrimRight`](#TrimRight)

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

#### See Also

- [`Trim`](#Trim)
- [`TrimLeft`](#TrimLeft)

---

### Lowercase

Converts to lowercase.

#### Syntax

```php
public function Lowercase(): \Harmonia\Core\CString
```

#### Return Value

A new `CString` instance with all characters converted to lowercase.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Uppercase`](#Uppercase)

---

### Uppercase

Converts to uppercase.

#### Syntax

```php
public function Uppercase(): \Harmonia\Core\CString
```

#### Return Value

A new `CString` instance with all characters converted to uppercase.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Lowercase`](#Lowercase)

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

#### See Also

- [`EndsWith`](#EndsWith)

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

#### See Also

- [`StartsWith`](#StartsWith)

---

### IndexOf

Finds the offset of the first occurrence of a string.

#### Syntax

```php
public function IndexOf(string|\Harmonia\Core\CString $searchString, int $startOffset = 0, bool $caseSensitive = true): int|null
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

### Split

Splits the string by a given delimiter, yielding each substring as a
`CString` instance.

This method provides memory-efficient processing by yielding each
substring one at a time, making it suitable for large strings.

By default, it performs a straightforward split without trimming or
excluding empty results. These behaviors can be customized with options.

#### Syntax

```php
public function Split(string $delimiter, int $options = self::SPLIT_OPTION_NONE): \Generator
```

#### Parameters

- **$delimiter**: The delimiter indicating the points at which each split should occur.
- **$options**: (Optional) Bitwise options for splitting behavior. `CString::SPLIT_OPTION_TRIM` trims whitespace from each substring, and `CString::SPLIT_OPTION_EXCLUDE_EMPTY` excludes empty substrings from the result. The default is `SPLIT_OPTION_NONE`, which applies no trimming or exclusion.

#### Return Value

A generator yielding `CString` instances for each substring.

#### See Also

- [`SplitToArray`](#SplitToArray)

---

### SplitToArray

Splits the string by a given delimiter and returns the result as an array
of `CString` instances.

This method is a convenient alternative to `Split`, returning the results
directly as an array of `CString` instances.

By default, it performs a straightforward split without trimming or
excluding empty results. These behaviors can be customized with options.

#### Syntax

```php
public function SplitToArray(string $delimiter, int $options = self::SPLIT_OPTION_NONE): \Harmonia\Core\CString[]
```

#### Parameters

- **$delimiter**: The delimiter indicating the points at which each split should occur.
- **$options**: (Optional) Bitwise options for splitting behavior. `CString::SPLIT_OPTION_TRIM` trims whitespace from each substring, and `CString::SPLIT_OPTION_EXCLUDE_EMPTY` excludes empty substrings from the result. The default is `SPLIT_OPTION_NONE`, which applies no trimming or exclusion.

#### Return Value

An array of `CString` instances for each substring.

#### See Also

- [`Split`](#Split)

---

### __toString

Returns the string representation for use in string contexts.

#### Syntax

```php
public function __toString(): string
```

#### Return Value

The string value stored in the instance.

---

### offsetExists

Provides array-like access to check if a character exists at a given offset.

#### Syntax

```php
public function offsetExists(mixed $offset): bool
```

#### Parameters

- **$offset**: The zero-based offset to check.

#### Return Value

Returns `true` if the offset is within range, `false` otherwise.

#### Exceptions

- **\InvalidArgumentException**: If the offset is not an integer.

---

### offsetGet

Provides array-like access to retrieve the character at a given offset.

#### Syntax

```php
public function offsetGet(mixed $offset): mixed
```

#### Parameters

- **$offset**: The zero-based offset of the character to return.

#### Return Value

The character at the specified offset, or an empty string if the offset is out of range.

#### Exceptions

- **\TypeError**: If the offset is not an integer.
- **\ValueError**: If an error occurs due to encoding.

---

### offsetSet

Provides array-like access to set the character at a specified offset.

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

Provides array-like access to delete the character at a specified offset.

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

Provides array-like traversal over each character.

#### Syntax

```php
public function getIterator(): \Traversable
```

#### Return Value

An iterator yielding each character.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
