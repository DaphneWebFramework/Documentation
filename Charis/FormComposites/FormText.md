# FormText

Abstract base class for standard form components with a label, input, and
optional help text.

Aside from HTML attributes that apply to the wrapper element, this component
supports the following pseudo attributes in its constructor:

- `:id`: A unique identifier for the input element. If omitted and a `:label`
  is provided, an ID is generated automatically.
- `:name`: The name attribute for the input element, used for grouping
  related inputs and identifying the input's value during form submission.
- `:label`: Text for the associated `<label>` element. If omitted, no label
  is rendered.
- `:help`: Additional descriptive text. If provided, a `<div>` element with
  the "form-text" class is rendered.
- `:placeholder`: Specifies a hint or short description that appears inside
  the input element when it is empty.
- `:disabled`: Boolean indicating whether the input should be disabled.
  Defaults to `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
