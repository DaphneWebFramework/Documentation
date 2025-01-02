# FormCheckableComposite

Abstract base class for checkable form components, such as `FormCheck`,
`FormRadio`, and `FormSwitch`.

Aside from HTML attributes that apply to the wrapper element, this component
supports the following pseudo attributes in its constructor:

- `:id`: A unique identifier for the input element. If omitted and a
  `:label-text` is provided, an ID is generated automatically.
- `:name`: The name attribute for the input element, used for grouping
  related inputs and identifying the input's value during form submission.
- `:label-text`: Text for the associated `<label>` element. If omitted, no
  label is rendered.
- `:help-text`: Additional descriptive text. If provided, a `<div>` element
  with the "form-text" class is rendered.
- `:checked`: Boolean indicating whether the input should be checked.
  Defaults to `false`.
- `:disabled`: Boolean indicating whether the input should be disabled.
  Defaults to `false`.

#### See Also

- [https://getbootstrap.com/docs/5.3/forms/checks-radios/](https://getbootstrap.com/docs/5.3/forms/checks-radios/)

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(array<string,bool|int|float|string>|null $attributes = null)
```

#### Parameters

- **$attributes**: (Optional) An associative array where HTML attributes apply to the wrapper element, and pseudo attributes configure inner child elements.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
