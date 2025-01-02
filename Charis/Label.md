# Label

Abstract base class for defining and rendering HTML components.

This class provides a foundation for creating server-side rendered HTML
components. Subclasses must implement the `getTagName` method to define the
specific HTML tag for the component. Optionally, subclasses can override:

- `getDefaultAttributes`: Defines default attributes for the component.
- `getMutuallyExclusiveClassAttributeGroups`: Defines class groups where only
  one class from each group can be applied at a time.
- `isSelfClosing`: Indicates whether the component is self-closing (e.g.,
  `<img/>`). Defaults to `false`.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
