# DataHelper

Provides reusable data sets for PHPUnit, including common value types like
non-strings, non-integers, booleans, and combinations of test data (Cartesian
product).

#### Example
```php
use \PHPUnit\Framework\TestCase;
use \PHPUnit\Framework\Attributes\DataProviderExternal;

use \TestToolkit\DataHelper;

class ExampleTest extends TestCase
{
    #[DataProviderExternal(DataHelper::class, 'NonStringProvider')]
    function testConstructorWithNonStringValue($value)
    {
        $this->expectException(\TypeError::class);
        new ExampleClass($value);
    }
}
```

## Methods

### BooleanProvider

Provides boolean values.

#### Syntax

```php
public static function BooleanProvider(): array
```

#### Return Value

Returns an array of boolean values.

---

### NonStringProvider

Provides non-string, non-Stringable values.

#### Syntax

```php
public static function NonStringProvider(): array
```

#### Return Value

Returns an array of non-string, non-Stringable values.

---

### NonStringExcludingNullProvider

Provides non-string, non-Stringable values, excluding `null`.

#### Syntax

```php
public static function NonStringExcludingNullProvider(): array
```

#### Return Value

Returns an array of non-string, non-Stringable values, excluding `null`.

---

### NonBooleanProvider

Provides non-boolean values.

#### Syntax

```php
public static function NonBooleanProvider(): array
```

#### Return Value

Returns an array of non-boolean values.

---

### NonIntegerProvider

Provides non-integer values.

#### Syntax

```php
public static function NonIntegerProvider(): array
```

#### Return Value

Returns an array of non-integer values.

---

### NonIntegerExcludingNumericStringProvider

Provides non-integer values, excluding strings that represent integers.

#### Syntax

```php
public static function NonIntegerExcludingNumericStringProvider(): array
```

#### Return Value

Returns an array of values that are neither integers nor stringified integers.

---

### NonStringOrIntegerProvider

Provides non-string, non-integer values.

#### Syntax

```php
public static function NonStringOrIntegerProvider(): array
```

#### Return Value

Returns an array of values that are neither strings nor integers.

---

### NonArrayProvider

Provides non-array values.

#### Syntax

```php
public static function NonArrayProvider(): array
```

#### Return Value

Returns an array of values that are not arrays.

---

### Cartesian

Generates the Cartesian product of multiple arrays.

This function is designed to calculate the cartesian product of multiple
arrays, which is particularly useful in PHPUnit data provider functions.
It is ideal for generating all possible combinations of test data from
multiple sets. The cartesian product operation results in an array of
arrays, each containing a unique combination of elements from the input
arrays.

#### Example
```php
static function dataProvider() {
    return DataHelper::Cartesian([1, 2, 3], ['a', 'b']);
}

// Returns: [1, 'a'], [1, 'b'], [2, 'a'], [2, 'b'], [3, 'a'], [3, 'b']
```

#### Syntax

```php
public static function Cartesian(array ...$arrays): array
```

#### Parameters

- **$arrays**: The input arrays for which the Cartesian product will be calculated.

#### Return Value

The Cartesian product as an array of arrays, representing all combinations.

#### See Also

- [Sergiy Sokolenko's answer on StackOverflow](https://stackoverflow.com/a/15973172)

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
