# CachedValue

Provides lazy caching of a nullable value.

The first time the value is accessed via `Get`, it is resolved by evaluating
the provided closure. The result is then cached, including `null` values, and
reused for subsequent calls.

## Methods

### Get

Returns the cached value if available; otherwise, resolves and caches it.

#### Syntax

```php
public function Get(callable $resolver): ?\Harmonia\Patterns\T
```

#### Parameters

- **$resolver**: A callable that provides the value if it has not been cached yet.

#### Return Value

The cached value, or the result of the resolver.

---

### Set

Manually sets the cached value and marks it as cached.

Useful for test injection or manually assigning a known value.

#### Syntax

```php
public function Set(?\Harmonia\Patterns\T $value): void
```

#### Parameters

- **$value**: The value to cache.

---

### IsCached

Checks whether the value has already been resolved and cached.

#### Syntax

```php
public function IsCached(): bool
```

#### Return Value

Returns `true` if the value has been cached; `false` otherwise.

---

### Reset

Clears the cached value and resets the cached state.

Useful for invalidation or forcing the value to be re-resolved.

#### Syntax

```php
public function Reset(): void
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
