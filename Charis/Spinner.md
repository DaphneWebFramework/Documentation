# Spinner

Represents a Bootstrap spinner.

Aside from HTML attributes that apply to the wrapper element, this component
supports the following pseudo attributes in its constructor:

- `:type` (string): The spinner style. Accepted values are 'border' and
  'grow'. Defaults to 'border'.
- `:size` (string): Size modifier. Only 'sm' is supported. Defaults to
  standard size.
- `:label` (string): Accessible text for screen readers. Defaults to
  "Loading...".

#### See Also

- [https://getbootstrap.com/docs/5.3/components/spinners/](https://getbootstrap.com/docs/5.3/components/spinners/)

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
