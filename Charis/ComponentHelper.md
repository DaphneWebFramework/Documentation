# ComponentHelper

Provides helper functions for component classes.

## Methods

### ResolveClasses

Resolve classes by merging default classes with user-defined classes,
handling duplicates and managing mutually exclusive groups.

#### Syntax

```php
public static function ResolveClasses(string $defaultClasses, string $userClasses, string[] $mutuallyExclusiveClassGroups = []): string
```

#### Parameters

- **$defaultClasses**: A space-separated string of default class names defined by the component (e.g., `'btn btn-default'`).
- **$userClasses**: A space-separated string of user-defined class names (e.g., `'btn-lg btn-primary'`).
- **$mutuallyExclusiveClassGroups**: (Optional) An array of space-separated strings representing mutually exclusive class groups (e.g., `['btn-default btn-primary btn-success', 'btn-sm btn-lg']`).

#### Return Value

A resolved and merged class string with duplicates removed and mutually exclusive conflicts resolved.

---

### ParseClassList

Parses a space-separated class string into an array of individual class
names, normalizing spaces and trimming extra whitespace.

#### Syntax

```php
public static function ParseClassList(string $classes): string[]
```

#### Parameters

- **$classes**: A space-separated string of class names (e.g., 'btn btn-primary').

#### Return Value

An array of class names. If the input string is empty or consists only of whitespace, an empty array is returned.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
