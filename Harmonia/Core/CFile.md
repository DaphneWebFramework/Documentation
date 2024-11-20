# CFile

Provides an interface for file operations.

## Methods

### __destruct

Destructor that closes the file handle if it hasn't been closed explicitly.

#### Syntax

```php
public function __destruct()
```

---

### Open

Opens a file and returns a new `CFile` instance.

#### Syntax

```php
public static function Open(string $filename, string $mode = self::MODE_READ): ?\Harmonia\Core\CFile
```

#### Parameters

- **$filename**: The name of the file to open.
- **$mode**: (Optional) The mode for opening the file. Defaults to `CFile::MODE_READ`.

#### Return Value

A `CFile` instance if successful, or `null` on failure.

---

### Close

Closes the file handle, making the instance unusable afterward.

#### Syntax

```php
public function Close(): void
```

---

### Read

Reads a specified number of bytes.

This method allows multiple readers to access the file concurrently,
while preventing other processes from writing to the file until the
reading is complete. If another process is currently writing to the file,
this call will efficiently wait until the write operation is finished.

#### Syntax

```php
public function Read(?int $length = null): ?string
```

#### Parameters

- **$length**: (Optional) The number of bytes to read. If omitted, reads until the end of the file.

#### Return Value

The read bytes as a string, or `null` on failure.

---

### ReadLine

Reads a line.

This method allows multiple readers to access the file concurrently,
while preventing other processes from writing to the file until the
reading is complete. If another process is currently writing to the file,
this call will efficiently wait until the write operation is finished.

#### Syntax

```php
public function ReadLine(): ?string
```

#### Return Value

The line read without newline characters, or `null` on read failure.

---

### Write

Writes the specified bytes.

This method prevents other processes from reading or writing to the file
while the write operation is in progress. If another process is currently
accessing the file, this call will efficiently wait until the file is
available for exclusive access.

#### Syntax

```php
public function Write(string $bytes): bool
```

#### Parameters

- **$bytes**: The string containing the bytes to write.

#### Return Value

Returns `true` if the write is successful, `false` otherwise.

---

### WriteLine

Writes a line.

This method automatically writes a newline character (`\n`) after the
line is written.

This method prevents other processes from reading or writing to the file
while the write operation is in progress. If another process is currently
accessing the file, this call will efficiently wait until the file is
available for exclusive access.

#### Syntax

```php
public function WriteLine(string $line): bool
```

#### Parameters

- **$line**: The line to write.

#### Return Value

Returns `true` if the write is successful, `false` otherwise.

---

### Size

Returns the file size in bytes.

#### Syntax

```php
public function Size(): int
```

#### Return Value

The file size in bytes, or `0` on failure.

---

### Cursor

Returns the current cursor position.

#### Syntax

```php
public function Cursor(): ?int
```

#### Return Value

The current position of the file cursor, or `null` on failure.

---

### SetCursor

Sets the cursor to a specified position.

#### Syntax

```php
public function SetCursor(int $offset, int $origin = self::ORIGIN_BEGIN): bool
```

#### Parameters

- **$offset**: The byte offset to move the cursor. This value is interpreted relative to the `$origin` parameter.
- **$origin**: (Optional) The reference position for `$offset`. Must be one of `ORIGIN_BEGIN`, `ORIGIN_CURRENT`, or `ORIGIN_END`. Defaults to `ORIGIN_BEGIN`.

#### Return Value

Returns `true` if the cursor was successfully moved, `false` otherwise.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
