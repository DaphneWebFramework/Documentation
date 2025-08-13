# Modal

Represents a modal dialog.

Aside from HTML attributes that apply to the wrapper `<div class="modal">`
element, this component supports the following pseudo attributes in its
constructor:

- `:title` (string): The text content of the modal title. Defaults to an
  empty string.
- `:body` (mixed): The content of the modal body. Can be a string, a
  `Component` instance, or an array of components. Defaults to an empty
  string.
- `:secondary-button:*` (mixed): Additional HTML attributes forwarded to
  the secondary footer button.
- `:secondary-button-label` (string): The label for the secondary footer
  button. Defaults to "Close".
- `:primary-button:*` (mixed): Additional HTML attributes forwarded to
  the primary footer button.
- `:primary-button-label` (string): The label for the primary footer button.
  Defaults to "Save changes".
- `:footer` (mixed): The entire content of the footer. When provided,
  completely overrides the default secondary/primary buttons. Can be a
  string, a `Component` instance, or an array of components. If set to
  `false`, the footer is entirely omitted.
- `:dialog:*` (mixed): Additional HTML attributes forwarded to the internal
  `<div class="modal-dialog">` element.

#### See Also

- [https://getbootstrap.com/docs/5.3/components/modal/](https://getbootstrap.com/docs/5.3/components/modal/)

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(?array<string,mixed> $attributes = null)
```

#### Parameters

- **$attributes**: (Optional) An associative array where standard HTML attributes apply to the wrapper element, and pseudo attributes configure internal structure. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
