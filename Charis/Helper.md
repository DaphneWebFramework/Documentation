# Helper

Contains utility functions intended for internal use by the `Component` class
and its subclasses.

## Methods

### MergeAttributes

Merges user-provided attributes with default attributes, producing a
final set of HTML attributes suitable for rendering.

If the `class` attribute is present, its values from both sources
are combined. When a mutually exclusive class group is defined
(e.g., `'btn-primary btn-secondary btn-success'`), only one class
from the group will be retained. User-supplied negative class directives
(e.g., `-btn-primary`) remove matching classes from the default list.
Additionally, if the user provides `false` as the class value, the entire
class attribute is removed from the result, overriding any default.

#### Syntax

```php
public static function MergeAttributes(?array<string,mixed> $userAttributes, array<string,mixed> $defaultAttributes, array<int,string> $mutuallyExclusiveClassGroups): array<string,mixed>
```

#### Parameters

- **$userAttributes**: Attributes provided by the user. Can be `null`.
- **$defaultAttributes**: Default attributes defined by the component.
- **$mutuallyExclusiveClassGroups**: Mutually exclusive class groups to resolve conflicts. Each group is a space-separated class names where only one class should survive.

#### Return Value

Final resolved attributes, suitable for rendering.

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
public static function ConsumePseudoAttribute(?array<string,mixed> &$attributes, string $key, mixed $defaultValue = null): mixed
```

#### Parameters

- **$attributes**: An associative array of attributes. The array will be modified in place by removing the specified pseudo attribute if found. Can be `null`.
- **$key**: The key of the pseudo attribute to consume. Keys must match the defined pattern and are case-sensitive.
- **$defaultValue**: (Optional) The value to return if the key is not present or invalid. Defaults to `null`.

#### Return Value

The value of the consumed pseudo attribute, or the default value if not found.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
