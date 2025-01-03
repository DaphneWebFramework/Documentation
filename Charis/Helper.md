# Helper

Contains utility functions intended for internal use by the `Component` class
and its subclasses.

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

### CombineClassAttributes

Merges two HTML `class` attribute strings into a single string with
duplicates removed.

#### Syntax

```php
public static function CombineClassAttributes(string $classes1, string $classes2): string
```

#### Parameters

- **$classes1**: A space-separated string of class names.
- **$classes2**: Another space-separated string of class names.

#### Return Value

A space-separated string containing all class names with duplicates removed.

---

### ConsumePseudoAttribute

Returns and removes the specified pseudo attribute from the given
attributes array.

#### Syntax

```php
public static function ConsumePseudoAttribute(array<string,bool|int|float|string>|null &$attributes, string $key, mixed $defaultValue = null): mixed
```

#### Parameters

- **$attributes**: An associative array of attributes. The array will be modified in place by removing the specified pseudo attribute if found.
- **$key**: The key of the pseudo attribute to consume. Keys must match the defined pattern and are case-sensitive.
- **$defaultValue**: (Optional) The value to return if the key is not present or invalid. Defaults to `null`.

#### Return Value

The value of the consumed pseudo attribute, or the default value if not found.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
