# NavbarDropdown

Represents a dropdown menu in a navigation bar.

Aside from HTML attributes that apply to the wrapper element, this component
supports the following pseudo attributes in its constructor:

- `:label`: The text for the dropdown toggle link. Defaults to an empty
  string.
- `:id`: The ID attribute for the dropdown toggle link.
- `:disabled`: Boolean indicating whether the dropdown is disabled. Defaults
  to `false`.
- `:alignRight`: Boolean indicating whether the dropdown menu should be
  aligned to the right. Defaults to `false`.

#### See Also

- [https://getbootstrap.com/docs/5.3/components/navbar/#nav](https://getbootstrap.com/docs/5.3/components/navbar/#nav)

## Methods

### __construct

Constructs a new instance.

#### Syntax

```php
public function __construct(?array<string,mixed> $attributes = null, (\Charis\NavbarDropdownItem|\Charis\NavbarDropdownDivider)[] $items = [])
```

#### Parameters

- **$attributes**: (Optional) An associative array where standard HTML attributes apply to the wrapper element, and pseudo attributes configure inner components. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.
- **$items**: (Optional) The dropdown menu items to render inside the dropdown container. Defaults to an empty array.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
