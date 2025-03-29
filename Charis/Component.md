# Component

Abstract base class for defining and rendering HTML components.

Subclasses must implement the `getTagName` method to specify the HTML tag
for the component. Subclasses can optionally override:

- `getDefaultAttributes`: Returns the default attributes for the component.
- `getMutuallyExclusiveClassAttributeGroups`: Specifies groups of CSS classes
  where only one class from each group can be applied simultaneously.
- `isSelfClosing`: Indicates whether the component is self-closing (e.g.,
  `<input/>`, `<img/>`).

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(?array<string,mixed> $attributes = null, string|\Charis\Component|(string|\Charis\Component)[]|null $content = null)
```

#### Parameters

- **$attributes**: (Optional) An associative array of HTML attributes, where keys are attribute names and values can be of type `bool`, `int`, `float`, `string`, or `Stringable`. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.
- **$content**: (Optional) The content or child elements of the component. This can be a string, a `Component` instance, an array of strings and `Component` instances, or `null` for no content. Defaults to `null`.

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

- **\InvalidArgumentException**: If the tag name does not match the required pattern, an attribute name is not a string or does not match the required pattern, an attribute value is not scalar, or the content array contains an item that is neither a string nor a `Component` instance.
- **\LogicException**: If the component is self-closing but has non-empty content.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
