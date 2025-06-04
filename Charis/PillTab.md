# PillTab

Represents a selectable item in a pill-based tab navigation.

Aside from HTML attributes that apply to the wrapper element, this component
supports the following pseudo attributes in its constructor:

- `:key` (string, required): A unique name used to associate this item with
  its corresponding content panel.
- `:active` (boolean): Indicates whether this item is initially active.
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

- **$attributes**: (Optional) An associative array where standard HTML attributes apply to the wrapper element, and pseudo attributes configure inner components. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.
- **$content**: (Optional) The content or child elements of the component. This can be a string, a `Component` instance, an array of strings and `Component` instances, or `null` for no content. Defaults to `null`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
