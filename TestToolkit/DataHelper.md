# DataHelper

Provides reusable data sets for PHPUnit, including common value types like
non-strings, non-integers, booleans, and combinations of test data (Cartesian
product).

## Methods

> ### Cartesian

Generates the Cartesian product of multiple arrays.

This function is designed to calculate the cartesian product of multiple
arrays, which is particularly useful in PHPUnit data provider functions.
It is ideal for generating all possible combinations of test data from
multiple sets. The cartesian product operation results in an array of
arrays, each containing a unique combination of elements from the input
arrays.

Example usage in PHPUnit data provider:
```php
public function dataProvider() {
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
