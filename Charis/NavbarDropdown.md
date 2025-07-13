# NavbarDropdown

Represents a dropdown navigation item in a navigation bar.

Aside from HTML attributes that apply to the wrapper `<li>` element, this
component supports the following pseudo attributes in its constructor:

- `:label` (string): The text content of the item. Defaults to an empty string.
- `:disabled` (boolean): Indicates whether the item is non-interactive.
  Defaults to `false`.
- `:link:*` (mixed): Additional HTML attributes forwarded to the internal
  `<a>` element.
- `:menu:*` (mixed): Additional HTML attributes forwarded to the internal
  `<ul>` element.

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

- **$attributes**: (Optional) An associative array where standard HTML attributes apply to the wrapper element, and pseudo attributes configure internal structure. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.
- **$items**: (Optional) The menu items to render inside the dropdown container. Defaults to an empty array.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
