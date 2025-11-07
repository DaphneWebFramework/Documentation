# FormSelect

Represents a select with a label and optional help text.

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(?array<string,mixed> $attributes = null, \Charis\FormComposites\Option[]|null $options = null)
```

#### Parameters

- **$attributes**: (Optional) An associative array where standard HTML attributes apply to the wrapper element, and pseudo attributes configure inner components. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.
- **$options**: (Optional) An array of options to render inside the select control. Defaults to `null`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
