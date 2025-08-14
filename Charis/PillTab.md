# PillTab

Represents a tab item in a pill-based tab navigation.

Aside from HTML attributes, this component supports the following pseudo
attributes in its constructor:

- `:key` (string): A unique name used to associate this tab item with its
  corresponding pane. This must be provided and must be a non-empty
  string.
- `:active` (boolean): Indicates whether this tab item is initially active.
  Defaults to `false`.

#### See Also

- [https://getbootstrap.com/docs/5.3/components/navs-tabs/#javascript-behavior](https://getbootstrap.com/docs/5.3/components/navs-tabs/#javascript-behavior)

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(?array<string,mixed> $attributes = null, string|\Charis\Component|(string|\Charis\Component)[]|null $content = null)
```

#### Parameters

- **$attributes**: (Optional) An associative array of HTML attributes and pseudo attributes. Defaults to `null`.
- **$content**: (Optional) The content or child elements of the component. This can be a string, a `Component` instance, an array of strings and `Component` instances, or `null` for no content. Defaults to `null`.

#### Exceptions

- **\InvalidArgumentException**: If the `:key` pseudo attribute is not provided or is an empty string.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
