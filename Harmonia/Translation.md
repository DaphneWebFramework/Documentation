# Translation

Abstract base class for managing translations across the application.

This class loads and merges translations from one or more JSON files,
supporting multiple languages. The current language is determined by
the "Language" configuration setting.

Subclasses must define their own translation sources by overriding
`filePaths()`.

The JSON files must contain a mapping of translation IDs to translation units,
where each translation unit consists of language codes mapped to translation
text. The structure follows this format:

**Example JSON structure:**
```json
{
  "welcome_message": {
    "en": "Welcome to our application!",
    "tr": "Uygulamamıza hoş geldiniz!",
    "se": "Välkommen till vår applikation!"
  },
  "logout_confirmation": {
    "en": "Are you sure you want to log out?",
    "tr": "Çıkış yapmak istediğinizden emin misiniz?",
    "se": "Är du säker på att du vill logga ut?"
  }
}
```

> Exceptions thrown within this class use fixed messages and are not subject
to localization or customization through the `Translation` class itself.

## Methods

### Get

Retrieves a translation in the current application language.

Additional arguments can be passed for string formatting within the
translation. For example: `Get('field_must_be_numeric', 'price')`

#### Syntax

```php
public function Get(string $translationId, mixed ...$args): string
```

#### Parameters

- **$translationId**: The identifier of the translation.
- **$args**: (Optional) Arguments for string formatting within the translation.

#### Return Value

The translation in the current language.

#### Exceptions

- **\RuntimeException**: When the translation ID or language is not found.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
