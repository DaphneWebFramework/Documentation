# AccessHelper

Provides access to non-public properties and methods using PHP's reflection
API, enabling modification and retrieval of otherwise inaccessible values.

While primarily intended for private and protected members, these methods
can also be used to access public properties and methods.

## Methods

### SetProperty

Sets the value of a property in an object.

#### Syntax

```php
public static function SetProperty(object $object, string $propertyName, mixed $propertyValue): void
```

#### Parameters

- **$object**: The object in which to set the non-public property value.
- **$propertyName**: The name of the non-public property.
- **$propertyValue**: The value to set for the specified property.

#### Exceptions

- **\ReflectionException**: If the property does not exist or cannot be accessed.
- **\Error**: If the property is read-only, a fatal error will be thrown when attempting to modify it.

---

### GetProperty

Retrieves the value of a property from an object.

#### Syntax

```php
public static function GetProperty(object $object, string $propertyName): mixed
```

#### Parameters

- **$object**: The object from which to retrieve the non-public property value.
- **$propertyName**: The name of the non-public property.

#### Return Value

The value of the specified property.

#### Exceptions

- **\ReflectionException**: If the property does not exist or cannot be accessed.

---

### SetStaticProperty

Sets the value of a static property in a class.

#### Syntax

```php
public static function SetStaticProperty(string $className, string $propertyName, mixed $propertyValue): void
```

#### Parameters

- **$className**: The name of the class in which to set the non-public static property value.
- **$propertyName**: The name of the non-public static property.
- **$propertyValue**: The value to set for the specified property.

#### Exceptions

- **\ReflectionException**: If the property does not exist or cannot be accessed.
- **\Error**: If the property is read-only, a fatal error will be thrown when attempting to modify it.

---

### GetStaticProperty

Retrieves the value of a static property from a class.

#### Syntax

```php
public static function GetStaticProperty(string $className, string $propertyName): mixed
```

#### Parameters

- **$className**: The name of the class from which to retrieve the non-public static property value.
- **$propertyName**: The name of the non-public static property.

#### Return Value

The value of the specified static property.

#### Exceptions

- **\ReflectionException**: If the property does not exist or cannot be accessed.

---

### SetMockProperty

Sets the value of a property in a mock object.

This method is specifically designed for use with mock objects in unit
tests, allowing for the modification of properties that are not publicly
accessible.

#### Syntax

```php
public static function SetMockProperty(string $className, object $mockObject, string $propertyName, mixed $propertyValue): void
```

#### Parameters

- **$className**: The name of the original class from which the mock object was instantiated.
- **$mockObject**: The mock object in which to set the non-public property value.
- **$propertyName**: The name of the non-public property.
- **$propertyValue**: The value to set for the specified property.

#### Exceptions

- **\ReflectionException**: If the property does not exist or cannot be accessed.
- **\Error**: If the property is read-only, a fatal error will be thrown when attempting to modify it.

---

### GetMockProperty

Retrieves the value of a property from a mock object.

This method is particularly useful in unit testing scenarios where there
is a need to access properties of mock objects that are not publicly
accessible.

#### Syntax

```php
public static function GetMockProperty(string $className, object $mockObject, string $propertyName): mixed
```

#### Parameters

- **$className**: The name of the original class from which the mock object was instantiated.
- **$mockObject**: The mock object from which to retrieve the non-public property value.
- **$propertyName**: The name of the non-public property.

#### Return Value

The value of the specified property.

#### Exceptions

- **\ReflectionException**: If the property does not exist or cannot be accessed.

---

### CallConstructor

Invokes the constructor of a given object or class.

If the first argument is an object, it calls the non-public constructor
of that object. If it's a string, it treats it as a class name and
creates a new instance of the class before calling its constructor.
In both cases, the object with the constructor invoked is returned.

#### Syntax

```php
public static function CallConstructor(object|string $objectOrClassName, ?array $args = null): object
```

#### Parameters

- **$objectOrClassName**: An object or a fully qualified class name.
- **$args**: (Optional) An array of arguments to pass to the constructor.

#### Return Value

The object with its constructor invoked.

#### Exceptions

- **\ReflectionException**: If the constructor cannot be accessed, or if the class does not exist when a class name is provided.

---

### CallMethod

Invokes a method on an object.

This method allows for the invocation of non-public methods, enabling
unit testing or advanced manipulation of otherwise inaccessible logic.

#### Syntax

```php
public static function CallMethod(object $object, string $methodName, ?array $args = null): mixed
```

#### Parameters

- **$object**: The object instance on which to invoke the non-public method.
- **$methodName**: The name of the non-public method to invoke.
- **$args**: (Optional) An array of arguments to pass to the method.

#### Return Value

The result of the invoked method.

#### Exceptions

- **\ReflectionException**: If the method does not exist or cannot be accessed.

---

### CallStaticMethod

Invokes a static method on a class.

This method allows for the invocation of non-public static methods,
enabling unit testing or advanced manipulation of otherwise inaccessible
logic.

#### Syntax

```php
public static function CallStaticMethod(string $className, string $methodName, ?array $args = null): mixed
```

#### Parameters

- **$className**: The name of the class on which to invoke the non-public static method.
- **$methodName**: The name of the non-public static method to invoke.
- **$args**: (Optional) An array of arguments to pass to the method.

#### Return Value

The result of the invoked method.

#### Exceptions

- **\ReflectionException**: If the method does not exist or cannot be accessed.

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
