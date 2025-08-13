# FormFloatingLabelComposite

Abstract base class for form composites, combining an input control with a
floating label and optional help text.

Aside from HTML attributes that apply to the wrapper element, this component
supports the following pseudo attributes in its constructor:

- `:label` (string): Text for the label element. If omitted, no label is
  rendered.
- `:label:*` (mixed): Additional HTML attributes forwarded to the label
  element.
- `:input:*` (mixed): Additional HTML attributes forwarded to the input
  element.
- `:help` (string): Text for additional help below the input. If omitted,
  no help text is rendered.
- `:help:*` (mixed): Additional HTML attributes forwarded to the help text
  element.

#### See Also

- [https://getbootstrap.com/docs/5.3/forms/floating-labels/](https://getbootstrap.com/docs/5.3/forms/floating-labels/)

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(?array<string,mixed> $attributes = null)
```

#### Parameters

- **$attributes**: (Optional) An associative array where standard HTML attributes apply to the wrapper element, and pseudo attributes configure inner components. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
