# FormCheckable

Abstract base class for checkable form components such as `FormCheck`,
`FormRadio`, and `FormSwitch`.

This component supports the following pseudo attributes in its constructor:

- `:id`: A unique identifier for the input element. If omitted and a
  `:label-text` is provided, an ID is generated automatically.
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

- **$attributes**: (Optional) An associative array of HTML attributes and pseudo attributes.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
