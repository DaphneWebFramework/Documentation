# NavbarDropdownItem

Represents an item inside a navbar dropdown menu.

Aside from HTML attributes that apply to the wrapper `<li>` element, this
component supports the following pseudo attributes in its constructor:

- `:label` (string): The text content of the item. Defaults to an empty string.
- `:href` (string): The target URL when the item is clicked. Defaults to "#".
- `:disabled` (boolean): Indicates whether the item is non-interactive.
  Defaults to `false`.
- `:link:*` (mixed): Additional HTML attributes forwarded to the internal
  `<a>` element.

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

- **$attributes**: (Optional) An associative array where standard HTML attributes apply to the wrapper element, and pseudo attributes configure internal structure. Pass `null` or an empty array to indicate no attributes. Defaults to `null`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
