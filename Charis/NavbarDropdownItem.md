# NavbarDropdownItem

Represents an item inside a navbar dropdown menu.

Aside from HTML attributes that apply to the wrapper element, this component
supports the following pseudo attributes in its constructor:

- `:label`: The text for the link. Defaults to an empty string.
- `:href`: The URL for the link. Defaults to `#`.
- `:id`: The ID attribute for the link. Defaults to `null`.
- `:disabled`: Boolean indicating whether the link is disabled. Defaults to
  `false`.

#### See Also

- [https://getbootstrap.com/docs/5.3/components/navbar/#nav](https://getbootstrap.com/docs/5.3/components/navbar/#nav)

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(?array<string,mixed> $attributes = null)
```

#### Parameters

- **$attributes**: (Optional) An associative array where standard HTML attributes apply to the wrapper element, and pseudo attributes configure the inner anchor. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
