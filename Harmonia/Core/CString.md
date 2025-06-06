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

- **$value**: (Optional) The string value to store. If omitted, defaults to an empty string. If given an instance of `CString` or a subclass, its value, encoding, and single-byte/multibyte status are copied. If given a `Stringable` instance, its string representation is used, and for a native string, the value is used directly.
- **$encoding**: (Optional) The encoding to use (e.g., 'UTF-8', 'ISO-8859-1'). If omitted or set to `null`, defaults to the return value of `mb_internal_encoding`. This parameter is ignored when `$value` is an instance of `CString` or a subclass. Note that encoding names are case-insensitive.

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

### Get

Returns the character at a specified offset.

#### Syntax

```php
public function Get(int $offset): string
```

#### Parameters

- **$offset**: The zero-based offset of the character to return.

#### Return Value

The character at the specified offset, or an empty string if the offset is out of range.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`SetInPlace`](#SetInPlace)

---

### SetInPlace

Sets the character at the specified offset.

#### Syntax

```php
public function SetInPlace(int $offset, string $character): self
```

#### Parameters

- **$offset**: The zero-based offset where the character will be set. If the offset is negative or greater than or equal to the length of the string, no changes will be made.
- **$character**: The character to set at the specified offset. If more than one character is provided, no changes will be made.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Get`](#Get)

---

### InsertInPlace

Inserts a substring at the specified offset.

#### Syntax

```php
public function InsertInPlace(int $offset, string|\Stringable $substring): self
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
- [`AppendInPlace`](#AppendInPlace)

---

### PrependInPlace

Inserts the specified string at the beginning.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function PrependInPlace(string|\Stringable $substring): self
```

#### Parameters

- **$substring**: The string to prepend.

#### Return Value

The current instance.

#### See Also

- [`Prepend`](#Prepend)
- [`InsertInPlace`](#InsertInPlace)

---

### Prepend

Inserts the specified string at the beginning.

#### Syntax

```php
public function Prepend(string|\Stringable $substring): static
```

#### Parameters

- **$substring**: The string to prepend.

#### Return Value

A new instance with the string prepended.

#### See Also

- [`PrependInPlace`](#PrependInPlace)
- [`InsertInPlace`](#InsertInPlace)

---

### AppendInPlace

Inserts the specified string at the end.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function AppendInPlace(string|\Stringable $substring): self
```

#### Parameters

- **$substring**: The string to append.

#### Return Value

The current instance.

#### See Also

- [`Append`](#Append)
- [`InsertInPlace`](#InsertInPlace)

---

### Append

Inserts the specified string at the end.

#### Syntax

```php
public function Append(string|\Stringable $substring): static
```

#### Parameters

- **$substring**: The string to append.

#### Return Value

A new instance with the substring appended.

#### See Also

- [`AppendInPlace`](#AppendInPlace)
- [`InsertInPlace`](#InsertInPlace)

---

### DeleteInPlace

Deletes a range of characters starting from the specified offset.

#### Syntax

```php
public function DeleteInPlace(int $offset, int $count = 1): self
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
public function Left(int $count): static
```

#### Parameters

- **$count**: The number of characters to return. If greater than or equal to the length of the string, the entire string is returned.

#### Return Value

A new instance with the leftmost characters, or an empty instance if `$count` is not positive.

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
public function Right(int $count): static
```

#### Parameters

- **$count**: The number of characters to return. If greater than or equal to the length of the string, the entire string is returned.

#### Return Value

A new instance with the rightmost characters, or an empty instance if `$count` is not positive.

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
public function Middle(int $offset, int $count = PHP_INT_MAX): static
```

#### Parameters

- **$offset**: The zero-based starting offset of the characters to return.
- **$count**: (Optional) The number of characters to return. If omitted, or if fewer characters are available from the offset, only the available characters are returned.

#### Return Value

A new instance with the specified middle characters, or an empty instance if `$offset` is out of range or `$count` is not positive.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Left`](#Left)
- [`Right`](#Right)

---

### TrimInPlace

Trims whitespace or specified characters from both sides of the string.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function TrimInPlace(?string $characters = null): self
```

#### Parameters

- **$characters**: (Optional) Characters to trim. Defaults to trimming whitespace characters.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Trim`](#Trim)
- [`TrimLeftInPlace`](#TrimLeftInPlace)
- [`TrimRightInPlace`](#TrimRightInPlace)

---

### Trim

Trims whitespace or specified characters from both sides of the string.

#### Syntax

```php
public function Trim(?string $characters = null): static
```

#### Parameters

- **$characters**: (Optional) Characters to trim. Defaults to trimming whitespace characters.

#### Return Value

A new instance with the trimmed string.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`TrimInPlace`](#TrimInPlace)
- [`TrimLeft`](#TrimLeft)
- [`TrimRight`](#TrimRight)

---

### TrimLeftInPlace

Trims whitespace or specified characters from the start (left) of the
string.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function TrimLeftInPlace(?string $characters = null): self
```

#### Parameters

- **$characters**: (Optional) Characters to trim. Defaults to trimming whitespace characters.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`TrimLeft`](#TrimLeft)
- [`TrimInPlace`](#TrimInPlace)
- [`TrimRightInPlace`](#TrimRightInPlace)

---

### TrimLeft

Trims whitespace or specified characters from the start (left) of the
string.

#### Syntax

```php
public function TrimLeft(?string $characters = null): static
```

#### Parameters

- **$characters**: (Optional) Characters to trim. Defaults to trimming whitespace characters.

#### Return Value

A new instance with the trimmed string.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`TrimLeftInPlace`](#TrimLeftInPlace)
- [`Trim`](#Trim)
- [`TrimRight`](#TrimRight)

---

### TrimRightInPlace

Trims whitespace or specified characters from the end (right) of the
string.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function TrimRightInPlace(?string $characters = null): self
```

#### Parameters

- **$characters**: (Optional) Characters to trim. Defaults to trimming whitespace characters.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`TrimRight`](#TrimRight)
- [`TrimInPlace`](#TrimInPlace)
- [`TrimLeftInPlace`](#TrimLeftInPlace)

---

### TrimRight

Trims whitespace or specified characters from the end (right) of the
string.

#### Syntax

```php
public function TrimRight(?string $characters = null): static
```

#### Parameters

- **$characters**: (Optional) Characters to trim. Defaults to trimming whitespace characters.

#### Return Value

A new instance with the trimmed string.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`TrimRightInPlace`](#TrimRightInPlace)
- [`Trim`](#Trim)
- [`TrimLeft`](#TrimLeft)

---

### LowercaseInPlace

Converts to lowercase.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function LowercaseInPlace(): self
```

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`UppercaseInPlace`](#UppercaseInPlace)
- [`Lowercase`](#Lowercase)

---

### Lowercase

Converts to lowercase.

#### Syntax

```php
public function Lowercase(): static
```

#### Return Value

A new instance with all characters converted to lowercase.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`LowercaseInPlace`](#LowercaseInPlace)
- [`Uppercase`](#Uppercase)

---

### UppercaseInPlace

Converts to uppercase.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function UppercaseInPlace(): self
```

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`LowercaseInPlace`](#LowercaseInPlace)
- [`Uppercase`](#Uppercase)

---

### Uppercase

Converts to uppercase.

#### Syntax

```php
public function Uppercase(): static
```

#### Return Value

A new instance with all characters converted to uppercase.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`UppercaseInPlace`](#UppercaseInPlace)
- [`Lowercase`](#Lowercase)

---

### Equals

Checks if this string is equal to another string.

#### Syntax

```php
public function Equals(string|\Stringable $other, bool $caseSensitive = true): bool
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
public function StartsWith(string|\Stringable $searchString, bool $caseSensitive = true): bool
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
public function EndsWith(string|\Stringable $searchString, bool $caseSensitive = true): bool
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
public function IndexOf(string|\Stringable $searchString, int $startOffset = 0, bool $caseSensitive = true): ?int
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

### ReplaceInPlace

Replaces all occurrences of a specified search string with a replacement
string.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function ReplaceInPlace(string|\Stringable $searchString, string|\Stringable $replacement, bool $caseSensitive = true): self
```

#### Parameters

- **$searchString**: The substring to search for.
- **$replacement**: The substring to replace each occurrence of the search string.
- **$caseSensitive**: (Optional) Whether the comparison should be case-sensitive. By default, it is case-sensitive.

#### Return Value

The current instance.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`Replace`](#Replace)

---

### Replace

Replaces all occurrences of a specified search string with a replacement
string.

#### Syntax

```php
public function Replace(string|\Stringable $searchString, string|\Stringable $replacement, bool $caseSensitive = true): static
```

#### Parameters

- **$searchString**: The substring to search for.
- **$replacement**: The substring to replace each occurrence of the search string.
- **$caseSensitive**: (Optional) Whether the comparison should be case-sensitive. By default, it is case-sensitive.

#### Return Value

A new instance with the replacements made.

#### Exceptions

- **\ValueError**: If an error occurs due to encoding.

#### See Also

- [`ReplaceInPlace`](#ReplaceInPlace)

---

### Split

Splits the string by a given delimiter, yielding each substring as a
new instance.

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

A generator yielding new instances for each substring.

#### See Also

- [`SplitToArray`](#SplitToArray)

---

### SplitToArray

Splits the string by a given delimiter and returns the result as an array
of new instances.

This method is a convenient alternative to `Split`, returning the results
directly as an array of new instances.

By default, it performs a straightforward split without trimming or
excluding empty results. These behaviors can be customized with options.

#### Syntax

```php
public function SplitToArray(string $delimiter, int $options = self::SPLIT_OPTION_NONE): static[]
```

#### Parameters

- **$delimiter**: The delimiter indicating the points at which each split should occur.
- **$options**: (Optional) Bitwise options for splitting behavior. `CString::SPLIT_OPTION_TRIM` trims whitespace from each substring, and `CString::SPLIT_OPTION_EXCLUDE_EMPTY` excludes empty substrings from the result. The default is `SPLIT_OPTION_NONE`, which applies no trimming or exclusion.

#### Return Value

An array of new instances for each substring.

#### See Also

- [`Split`](#Split)

---

### ApplyInPlace

Applies a function to the current value.

This version of the method directly modifies the current instance.

#### Syntax

```php
public function ApplyInPlace(callable $function, mixed ...$args): self
```

#### Parameters

- **$function**: The function to apply to the current value. It must accept a string as its first parameter. Any additional arguments passed to this method will be forwarded to the applied function.
- **$args**: Additional arguments to pass to the applied function.

#### Return Value

The current instance.

#### Exceptions

- **\UnexpectedValueException**: If the applied function returns a value that is not a string.

#### See Also

- [`Apply`](#Apply)

---

### Apply

Applies a function to the current value.

#### Syntax

```php
public function Apply(callable $function, mixed ...$args): static
```

#### Parameters

- **$function**: The function to apply to the current value. It must accept a string as its first parameter. Any additional arguments passed to this method will be forwarded to the applied function.
- **$args**: Additional arguments to pass to the applied function.

#### Return Value

A new instance containing the result of the applied function.

#### Exceptions

- **\UnexpectedValueException**: If the applied function returns a value that is not a string.

#### See Also

- [`ApplyInPlace`](#ApplyInPlace)

---

### Match

Matches the string against a regular expression pattern.

#### Syntax

```php
public function Match(string $pattern, int $options = self::REGEX_OPTION_NONE, string $delimiter = '/'): ?array
```

#### Parameters

- **$pattern**: The regular expression pattern to match. The pattern should not include delimiters. For example, use `^foo` instead of `/^foo/`. The delimiter can be specified separately using the `$delimiter` parameter.
- **$options**: (Optional) Bitwise options for the regular expression match. The default is `REGEX_OPTION_NONE`. This value can be a combination of the following options: `REGEX_OPTION_CASE_INSENSITIVE`, `REGEX_OPTION_MULTILINE`.
- **$delimiter**: (Optional) The delimiter to use for the regular expression pattern in single-byte mode. The default is `/`. If the encoding is multibyte, the delimiter is ignored.

#### Return Value

An array of matches if the pattern is found, or `null` if no match is found.

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
