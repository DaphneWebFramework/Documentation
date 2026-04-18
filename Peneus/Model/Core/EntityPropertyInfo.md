# EntityPropertyInfo

Provides information about an entity property.

## Methods

### From

#### Syntax

```php
public static function From(\ReflectionType $reflectionType): ?self
```

#### Parameters

- **$reflectionType**

---

### Type

#### Syntax

```php
public function Type(): \Peneus\Model\Core\EntityPropertyType
```

---

### Class

#### Syntax

```php
public function Class(): string
```

---

### IsNullable

#### Syntax

```php
public function IsNullable(): bool
```

---

### DefaultValue

#### Syntax

```php
public function DefaultValue(): mixed
```

---

### EnumBackingType

#### Syntax

```php
public function EnumBackingType(): ?string
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
