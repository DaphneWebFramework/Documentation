# FormStandardComposite

Abstract base class for form composites, combining an input control with a
label and optional help text.

Aside from HTML attributes that apply to the wrapper element, this component
supports the following pseudo attributes in its constructor:

- `:id`: A unique identifier for the input element. If omitted and a `:label`
  is provided, an ID is generated automatically.
- `:name`: The name attribute for the input element, used to identify the
  input's value during form submission.
- `:value`: The initial value of the input element.
- `:label`: Text for the associated `<label>` element. If omitted, no label
  is rendered.
- `:help`: Additional descriptive text. If provided, a `<div>` element with
  the "form-text" class is rendered.
- `:placeholder`: Specifies a hint or short description that appears inside
  the input element when it is empty.
- `:autocomplete`: Provides a hint to browsers for autofilling the input
  field with previously entered data.
- `:disabled`: Boolean indicating whether the input should be disabled.
  Defaults to `false`.
- `:required`: Boolean indicating whether the input is required. Defaults to
  `false`.

#### See Also

- [https://getbootstrap.com/docs/5.3/forms/form-control/](https://getbootstrap.com/docs/5.3/forms/form-control/)

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
