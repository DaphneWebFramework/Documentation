# Mailer

Provides a unified mailer facade that selects and configures the appropriate
mailer implementation.

In development mode, this class delegates to a fake mailer. Otherwise, it
uses application settings to configure transport, authentication, sender, and
logging parameters, and delegates to a real SMTP-backed implementation.

## Methods

### __construct

Constructs a new instance using application configuration.

#### Syntax

```php
public function __construct()
```

---

### SetAddress

#### Syntax

```php
public function SetAddress(string $email): static
```

#### Parameters

- **$email**

---

### SetSubject

#### Syntax

```php
public function SetSubject(string $subject): static
```

#### Parameters

- **$subject**

---

### SetBody

#### Syntax

```php
public function SetBody(string $body): static
```

#### Parameters

- **$body**

---

### Send

#### Syntax

```php
public function Send(): bool
```

---

*This documentation was automatically generated using [phpDocumentor](http://www.phpdoc.org/) with the [Calliope](https://github.com/DaphneWebFramework/Calliope) template.*
