# Component

Represents an abstract base for HTML-like components.

## Methods

### __toString

Converts the component to its HTML string representation.

#### Syntax

```php
public function __toString(): string
```

#### Return Value

The HTML string representation of the component.

#### Exceptions

- **\InvalidArgumentException**: If the tag name is empty, contains invalid characters, an attribute name is not a string, is empty, an attribute value is not scalar, or the content array contains an item that is neither a string nor a `Component` instance.
- **\LogicException**: If the component is self-closing but has non-empty content.

---

### Render

Generates the HTML string representation of the component.

#### Syntax

```php
public function Render(): string
```

#### Return Value

The HTML string representation of the component.

#### Exceptions

- **\InvalidArgumentException**: If the tag name is empty, contains invalid characters, an attribute name is not a string, is empty, an attribute value is not scalar, or the content array contains an item that is neither a string nor a `Component` instance.
- **\LogicException**: If the component is self-closing but has non-empty content.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
