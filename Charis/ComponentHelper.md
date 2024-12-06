# ComponentHelper

Provides helper functions for component classes.

## Methods

### MergeAttributes

Resolves attributes by merging defaults, resolving classes, and handling
mutually exclusive class groups.

#### Syntax

```php
public static function MergeAttributes(array<string,bool|int|float|string> $defaultAttributes, array<string,bool|int|float|string>|null $userAttributes = null, string[] $mutuallyExclusiveClassGroups = []): array<string,bool|int|float|string>
```

#### Parameters

- **$defaultAttributes**: Default attributes defined by the component.
- **$userAttributes**: (Optional) Attributes provided by the user.
- **$mutuallyExclusiveClassGroups**: (Optional) Mutually exclusive class groups to resolve conflicts.

#### Return Value

Resolved attributes ready for rendering.

---

### ResolveClasses

Resolve classes by merging default classes with user-defined classes,
handling duplicates and managing mutually exclusive groups.

#### Syntax

```php
public static function ResolveClasses(string $defaultClasses, string $userClasses, string[] $mutuallyExclusiveClassGroups = []): string
```

#### Parameters

- **$defaultClasses**: A space-separated string of default class names defined by the component (e.g., `'btn btn-primary'`).
- **$userClasses**: A space-separated string of user-defined class names (e.g., `'btn-lg btn-primary'`).
- **$mutuallyExclusiveClassGroups**: (Optional) An array of space-separated strings representing mutually exclusive class groups (e.g., `['btn-primary btn-secondary btn-success', 'btn-sm btn-lg']`).

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
