# Generic

Represents a general-purpose HTML element.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(string $tagName, ?array<string,mixed> $attributes = null, string|\Charis\Component|(string|\Charis\Component)[]|null $content = null, bool $isSelfClosing = false)
```

#### Parameters

- **$tagName**: The HTML tag name for the component (e.g., "div", "span").
- **$attributes**: (Optional) An associative array of HTML attributes, where keys are attribute names and values can be of type `bool`, `int`, `float`, `string`, or `Stringable`. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.
- **$content**: (Optional) The content or child elements of the component. This can be a string, a `Component` instance, an array of strings and `Component` instances, or `null` for no content. Defaults to `null`.
- **$isSelfClosing**: (Optional) Indicates whether the component is self-closing (e.g., `<img/>`). Defaults to `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
