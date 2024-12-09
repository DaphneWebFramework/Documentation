# FormCheck

Represents a Bootstrap Check component.

This component supports the following pseudo attributes in its constructor:
- `:id`: A unique identifier for the input element. If omitted, a generated
  ID will be used if `:label-text` is provided.
- `:label-text`: The text content for the associated label. If present, a
  `<label>` element will be rendered.
- `:help-text`: Additional descriptive text. If present, a `<div>` element
  will be rendered.
- `:checked`: A boolean indicating whether the input should be checked.
  Defaults to `false`.
- `:disabled`: A boolean indicating whether the input should be disabled.
  Defaults to `false`.

Standard HTML attributes (e.g., `class`, `style`, `data-*`) can also be
passed in the `$attributes` parameter and will be merged with the component's
default attributes.

#### See Also

- [https://getbootstrap.com/docs/5.3/forms/checks-radios/#checks](https://getbootstrap.com/docs/5.3/forms/checks-radios/#checks)

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
