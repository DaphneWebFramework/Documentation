# Component

Abstract base class for defining and rendering HTML components.

This class provides a foundation for creating server-side rendered HTML
components. Subclasses must implement the `getTagName` method to define the
specific HTML tag for the component. Optionally, subclasses can override:

- `getDefaultAttributes`: Defines default attributes for the component.
- `getMutuallyExclusiveClassAttributeGroups`: Defines class groups where only
  one class from each group can be applied at a time.
- `isSelfClosing`: Indicates whether the component is self-closing (e.g.,
  `<img/>`). Defaults to `false`.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(array<string,bool|int|float|string>|null $attributes = null, string|\Charis\Component|(string|\Charis\Component)[]|null $content = null)
```

#### Parameters

- **$attributes**: (Optional) An associative array of HTML attributes, where keys are attribute names and values can be scalar types (`bool`, `int`, `float`, or `string`). Pass `null` or an empty array to indicate no attributes. Defaults to `null`.
- **$content**: (Optional) The content of the component, which can be a string, a single `Component` instance, an array of strings and `Component` instances, or `null` for no content. Defaults to `null`.

---

### __toString

Converts the component to its HTML string representation.

This method simply calls the `Render` method, performs no additional
processing.

#### Syntax

```php
public function __toString(): string
```

#### Return Value

The HTML string representation of the component.

#### Exceptions

- **\InvalidArgumentException**: If the `Render` method throws this exception.
- **\LogicException**: If the `Render` method throws this exception.

#### See Also

- [`Render`](#Render)

---

### Render

Generates the HTML string representation of the component.

#### Syntax

```php
public function Render(): string
```

#### Return Value

The HTML string representation of the component.

#### Exceptions

- **\InvalidArgumentException**: If the tag name is empty, contains invalid characters, an attribute name is not a string, is empty, an attribute value is not scalar, or the content array contains an item that is neither a string nor a `Component` instance.
- **\LogicException**: If the component is self-closing but has non-empty content.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
